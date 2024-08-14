---
title: "빠르고 안정적인 자율주행 기술을 향하여"
scope:
  type: posts
values:
  layout: single
  author_profile: true
  read_time: true
  comments: true
  share: true
  related: true
toc: true
toc_sticky: true
toc_label: "빠르고 안정적인 자율주행 기술을 향하여"
category: Meditation
tags: [최적제어이론, 자율주행, 모델기반제어, 정보이론]
lang: kr
header:
  teaser: "/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/0.webp"
image: assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/0.webp
---

<style>
  .centered-container {
      text-align: center;
  }
  figure {
      display: inline-block;
      margin: auto;
      padding: 10px;
      text-align: center;
      background-color: #fff;
  }
  figcaption {
      font-family: "Wanted Sans Variable", "Wanted Sans";
      font-size: 12px;
      color: #555;
      margin-top: 5px;
  }

  /* 새로 추가된 스타일 */
  .two-fig-container {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 20px; /* 이미지 간의 간격 */
      flex-wrap: wrap; /* 화면이 좁아질 때 이미지를 세로로 배치 */
  }
  .two-fig-container figure {
      width: calc(50% - 20px); /* 두 개의 figure가 나란히 배치되도록 설정 */
      box-sizing: border-box; /* 패딩과 보더를 포함하여 너비 계산 */
  }

  /* 작은 화면에서 각 figure를 세로로 배치 */
  @media (max-width: 768px) {
      .two-fig-container figure {
          width: 100%; /* 작은 화면에서는 figure가 전체 너비를 차지 */
      }
  }
</style>

> "우리가 살아가는 세상은 복잡하고(Complex), 비선형적이며(Noninear), 불확실하다(Uncertain). 우리는 어떻게 이렇게 혼란스러운 세상 속에서 궁극적인 전략을 생성하여 영속할 수 있는 걸까? 우리는 로봇들로 하여금 그러한 전략을 스스로 학습하고 발견하게 할 수 있을까?"

<div class="centered-container">
  <figure>
    <iframe src="https://giphy.com/embed/AS4N79Rt53Ss2rdVIg" width="480" height="319" style="" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
    <figcaption>
      사막과 같은 미끄럽고 울퉁불퉁한 곳에서 운전하는 모습, 출처: <a href="https://giphy.com/gifs/offroad-monster-energy-canam-AS4N79Rt53Ss2rdVIg">GIPHY</a></p>
    </figcaption>
  </figure>
</div>

차량, 로봇, 원전 등 다양한 기계 장치에 대해 생각해보자. 그들은 모두 센서, 볼트와 너트, 모터 등의 작은 기계 장치들로 구성된 **시스템(System)**이다. 우리는 이러한 시스템이 우리가 원하는 대로 적절한 행동을 수행하길 바란다. 운전(Driving)의 문제를 생각해보자. 우리는 매일 아침과 저녁, 우리 눈과 귀를 활용해 먼 곳에서 가까운 곳까지 지각하여, 오른 발의 페달을 적절히 제어하며 운전해 나간다. 이러한 행동을 모사해내는 기계장치 혹은 소프트웨어를 구현하려면 어떻게 해야 할까?

본 글은 **자율 주행(Autonomous Driving)** 분야와 관련된 **최적 제어 이론(Optimal Control Theory)**을 공부하며 깨달은 부분들을 쉽고 간결하게 정리하는 것을 목표로 한다. 특히, 최근 강화학습과 더불어 각광받는 **모델 기반 예측 제어(Model Predictive Control, 이하 MPC)**에서 유명한 **정보 이론 기반의 MPC(Information-Theoretic MPC)** 알고리즘을 다루려고 한다.

---

# 1. 최적 제어 이론의 창시

이러한 제어의 문제는 과거 사이버네틱스 운동에서 깊게 다뤄졌으며, **최적 제어 이론(Optimal Control Theory; 이하 OCT)**으로 발전하게 되었다. 이 분야는 기계 장치로 하여금, 그들이 취할 수 있는 행동 중 우리가 원하는 최적의 행동을 하게 하기 위한 이론적 프레임워크와 공학적 설계 방법론을 제공해준다. 최적 제어 이론은 강력한 수학적 배경지식을 요구한다. 왜냐하면, 이 분야는 서로 다른 두 명의 천재 수학자; 미국의 **[리처드 벨만(Richard E. Bellman)](https://en.wikipedia.org/wiki/Richard_E._Bellman)**과 구 소비에트 연방의 **[레프 폰트랴긴(Лев Семёно́вич Понтря́гин)](https://en.wikipedia.org/wiki/Lev_Pontryagin)**에 의해 창시되었기 때문이다.

## 1.1 리처드 벨만과 레프 폰트랴긴

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/1.jpg" style="width: 60%; height: auto;">
      <figcaption>
        미국의 리처드 벨만(Richard E. Bellman), 출처: 위키피디아.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/2.jpg" style="width: 55%; height: auto;">
      <figcaption>
        소비에트 연방의 레프 폰트랴긴(Лев Семёно́вич Понтря́гин), 출처: <a href="https://timenote.info/en/Lev-Pontryagin">타임노트</a>
      </figcaption>
    </figure>
  </div>
</div>

먼저, 자신의 자서전 "[태풍의 눈(Eye of the Hurricane)](https://www.amazon.com/Hurricane-Autobiography-Richard-Ernest-Bellman/dp/9971966018)"으로도 유명한 벨만은 과거 1950년대 RAND(Research and Development) 연구소에서 미사일의 제어와 관련된 문제를 다루게 된다. 벨만은 컴퓨터 공학과의 알고리즘 수업에서 반드시 배우는 **[동적 프로그래밍(Dynamic Programming)](https://en.wikipedia.org/wiki/Dynamic_programming)**의 발명자이다. 동적 프로그래밍이란 문제의 **재귀성(Recursivity)**을 활용해 반복적인(Iterative) 계산과 메모리 할당으로 복잡한 문제를 쉽게 푸는 방법이다. 그는 자신의 알고리즘을 과거 19세기 물리학자/수학자 [해밀턴(William Rowan Hamilton)](https://en.wikipedia.org/wiki/William_Rowan_Hamilton)과 [자코비(Carl Gustav Jacob Jacobi)](https://en.wikipedia.org/wiki/Carl_Gustav_Jacob_Jacobi)가 입자의 움직임을 파동으로 표현한 **[해밀턴-자코비 방정식(Hamilton-Jacobi Equation)](https://en.wikipedia.org/wiki/Hamilton%E2%80%93Jacobi_equation)**에 적용한다. 이를 후대에는 **[해밀턴-자코비-벨만 방정식(Hamilton-Jacobi-Bellman Equation)](https://en.wikipedia.org/wiki/Hamilton%E2%80%93Jacobi%E2%80%93Bellman_equation)**이라고 부르며, 줄여서 HJB 방정식이라고 부른다.

한편, 폰트랴긴은 눈이 보이지 않는 시각 장애를 가졌음에도 다양한 분야에서 괄목할 만한 업적을 남긴 것으로 유명하다. 그는 **[폰트랴긴 최소 원리(Pontryagin's maximum principle)](https://en.wikipedia.org/wiki/Pontryagin%27s_maximum_principle)**를 통해 벨만의 HJB 방정식 유도와 유사한 결론을 얻었다. 그는 보다 엄밀하고 풍부한 수학을 사용했는데, 그의 이론은 추후 노벨 경제학상을 수상한 [칸토로비치](https://ko.wikipedia.org/wiki/%EB%A0%88%EC%98%A4%EB%8B%88%ED%8A%B8_%EC%B9%B8%ED%86%A0%EB%A1%9C%EB%B9%84%EC%B9%98)에 의해 경제학에 적용되었다. 

폰트랴긴의 접근법은 수학적으로 상미분 방정식을 활용했으며, 그의 접근은 해밀토니안 방정식과 유사하다는 특징이 있다. 다만, 경계 조건에 의존적이라 실제로 푸는 데 어려움이 있었다. 한편, 벨만의 접근법은 편미분 방정식을 활용하여, 이후 추가적인 잡음(noise) 항을 추가하기 용이했다. 물론, 차원의 저주로 인해 문제를 풀어내는 데에는 문제가 있었다.


## 1.2 이산 시간 최적 제어 문제

최적 제어 문제(Optimal Control Problem)은 총 세 가지 개념으로 구성된다. 먼저, 시간, 공간, 제어 변수에 의해 변화하는 동역학계가 주어져야 한다. 먼저 이산 시간에 따른 동역학계를 고려하자. 시간 변수를 $t$, 시스템의 변수를 $x_t$, 제어 변수를 $u_t$라고 하자. 그러면 아래 수식에서 $f$가 바로 동역학계를 의미한다:

$$
x_{t+1} = f(t, x_t, u_t), \ \  t= 0,1,...,T \cdots (1)
$$

이 동역학계는 특정 시간, 상태와 제어에 따라 보상(벨만) 또는 비용(폰트랴긴) $R(t,x_t,u_t)$이 있으며, 이를 활용해 주어진 시간 동안의 누적 비용 $C(x_0,u_{0:T})$을 말할 수 있게 된다. 이때 누적 비용 $C(x_0,u_{0:T})$가 초기 시스템 상태 $x_0$와 제어 입력들 $u_{0:T}$에만 의존하는 이유는 두 가지 정도로 표현할 수 있겠다. 첫번째 이유는 초기값과 이후 입력만 주어지면 동역학계 $f$를 통해 전체 시스템의 궤적을 계산할 수 있기 때문이다. 두번째는, 실무적 관점에서 각 시점의 시스템 상태는 센서를 통해 추론되는 경우가 많으므로 초기값 외에는 모른다고 가정하는 것이 합리적이기 때문이다:  

$$
C(x_0, u_{0:T}) = \sum_{t=0}^{T} R(t,x_t,u_t) \cdots (2)
$$

이제 최소 비용을 주는 최적 입력에 대해 말할 수 있다. 최적 입력(Optimal Control) $J(t, x_t)$는 현재 시점 $t$를 기준으로 앞으로 특정 시간 $T$까지의 비용을 최소로 만들어주는 입력이다. 즉:

$$
J(t, x_t) = \min_{u_{t:T}} \sum_{s=t}^{T} R(s,x_s,u_s) \cdots (3)
$$

이때, 최적 입력은 재귀 관계(Recursive Relation)을 갖는다. 이는 아래의 수식 전개를 통해 잘 드러나며, $J(t,x_t)$는 $J(t+1,x_{t+1})$로부터 계산될 수 있음을 보여준다:

$$
\begin{align} 
	\underline{J(t,x_t)} & = \min_{u_{t:T}} \sum_{s=t}^{T} R(s,x_s,u_s) \ by\ definition \\ 
    	& = \min_{u_t}\left( R(t,x_t,u_t) + \min_{u_{t+1:T}} \sum_{s=t+1}^{T} R(s,x_s,u_s) \right) \\ 
      & =\min_{u_t}\left( R(t,x_t,u_t) + J(t+1, x_{t+1}) \right) \\
      & =\min_{u_t}\left( R(t,x_t,u_t) + \underline{J(t+1, f(t,x_t,u_t))} \right) \cdots (4)
\end{align} 
$$

위 관계식으로부터 벨만의 동적 프로그래밍을 적용하면 원하는 시점 $T$ 이후부터는 $J(T+1,x)=0$으로 초기화한 후, 역으로 계산해 최적 입력을 계산해 나갈 수 있다. 

## 1.3 연속 시간 최적 제어 문제

이산 시간에서의 최적 문제와 관련된 수식 (1), (2), (3), (4)와 마찬가지로, 연속 시간 $t$에 따른 실변수 $x, u$에 대해 생각해볼 수 있다. 먼저, 문제의 구성요소는 다음과 같이 표현할 수 있다. 이때, $\phi(x(t_f))$는 최종 시스템 상태에 대한 특수 비용을 의미한다:

$$
\begin{align} 
  \dot{x} & = f(x,u,t) \cdots (5)\\
  C(t_i, x_i, u(t_i \rightarrow t_f)) & = \phi(x(t_f)) + \int_{t_i}^{t_f} dt R(x(t),u(t),t) \cdots (6)\\
  J(t,x) & = \min_{u(t_i \rightarrow t_f)} C(t,x,u(t \rightarrow t_f)) \cdots (7)\\
\end{align} 
$$

그러면, 최적 입력 $J(t,x)$는 수식 (4)와 같이 다음과 같은 재귀 관계를 지니게 된다(수식 전개 과정은 생략한다):

$$
\underline{J(t,x)} = \min_{u(t \rightarrow t')} \left( \int_{t}^{t'} dt R(x(t),u(t),t) + \underline{J(t', x(t'))} \right) \cdots (8)
$$

이때, $t'$가 $t$와 아주 작은 시간 간격 이후라고 가정하면; 즉, $t' = t + dt$을 대입하고 $dt \rightarrow 0$의 극한을 취하면 다음과 같은 편미분 방정식을 얻을 수 있다. 이 방정식이 바로 **HJB 방정식**이다.

$$
\begin{align} 
  - J_t(t,x) & = \min_{u} \left( R(x,u,t) + J_x(t,x)f(x,u,t) \right) \\
  J(x,t_f) & = \phi(x)
\end{align}  \cdots (9)
$$ 

---

<br>

# 2. 확률적 최적 제어 이론으로의 발전

기존의 최적 제어 이론은 훌륭한 이론적 프레임워크를 제안하는 데에는 성공했으나, 컴퓨터를 활용해 해답을 구하는 과정이 너무나 오래 걸렸다. 이에 더해, 동역학계 모델 $f$를 역으로 추정하거나 변수 $x$의 참값을 측정하거나 정확한 입력 $u$를 적용하는 데에도 한계가 있었다. 그러던 와중, HJB 방정식에 잡음 항을 추가함으로써 이를 해결하기 시작했다.

## 2.1 위너 프로세스

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/brownian.gif" style="width: 100%; height: auto;">
    <figcaption>
      브라운 운동. 수학적으로는 위너 프로세스로 표현된다.
    </figcaption>
  </figure>
</div>

수학에서 **위너 과정(Wiener Process)**은 미국의 수학자이자 사이버네틱스 운동의 창시자인 **[노버트 위너(Norbert Wiener)](https://en.wikipedia.org/wiki/Norbert_Wiener)**에 의해 발견된 연속 시간 확률 과정(Continuous-Time Stochastic Process)이다. 이는 종종 아인슈타인이 연구했던 브라운 운동(Brownian Motion)으로도 표현되는데 형식적으로는 깊은 관계를 갖는다. 자연스러운 현상에서는 대부분 잡음이 반영되며, 수많은 확률 과정에서 발견할 수 있다. 기존의 최적 제어 이론은 결정론적인 가정을 도입하여 확률의 개입을 막았지만, 수많은 실제 문제에서는 확률 과정의 도입이 필요해 보인다. 


위너 확률 과정 $W_t$의 특징은 다음과 같다:
  1. $W_0 = 0$.
  2. 임의의 $t>0$에 대해, 미래의 변화량 $W_{t+u} - W_t, u \leq 0$은 과거의 값들 $s < t$인 $W_s$에 대해 독립이다.
  3. $W_{t+u} - W_t \sim \mathit{N}(0, \nu)$.
  4. $W_t$는 $t$에 대해 연속이다.

미적분과 관련해, 위너 확률 과정의 시간에 대한 변화량 $d\xi$는 다음과 같은 성질을 지닌다.

$$
<d\xi^2> = \nu dt \cdots (10)
$$

## 2.2 확률적 최적 제어 문제

앞서 연속 시간 최적 제어 문제의 수식 (5), (6), (7), (8)에 대해 위너 과정 기반의 잡음 항을 추가할 수 있다. 이렇게 추가된 확률적 최적 제어 문제는 다음과 같이 기술할 수 있다. 수식 (13)에서 또한 재귀 관계를 확인할 수 있다:

$$
\begin{align} 
  dx & = f(x(t),u(t),t)dt + d\xi \cdots (11)\\
  C(t_i, x_i, u(t_i \rightarrow t_f)) & = \biggl< \phi(x(t_f)) + \int_{t_i}^{t_f} dt R(x(t),u(t),t) \biggr>_{x_i} \cdots (12)\\
  \underline{J(t,x)} & = \min_{u(t_i \rightarrow t_f)} \biggl<  \int_{t}^{t'} dt R(x(t),u(t),t) + \underline{J(t', x(t'))} \biggr>_{x} \cdots (13)\\
\end{align} 
$$

이때, $t'$가 $t$와 아주 작은 시간 간격 이후라고 가정하면; 즉, $t' = t + dt$을 대입하고 $dt \rightarrow 0$의 극한을 취하면 다음과 같은 편미분 방정식을 얻을 수 있다. 특히 아래 식을 얻는 과정에서 수식 (10)을 적용하여 확률변수의 증분 제곱의 평균 $<d\xi^2>$을 해당 위너 프로세스의 분산 $\nu dt$로 대체할 수 있다. 이렇게 얻은 아래의 방정식이 바로 **확률적 해밀턴-자코비-벨만 방정식(Stochastic Hamilton-Jacobi-Bellman Equation; sHJB)**이다.

$$
\begin{align} 
  - \partial_{t} J(t,x) & = \min_{u} \left( R(x,u,t) + f(x,u,t)^{T} \partial_{x} J(t,x) + \frac{1}{2}\nu \partial_{x}^2J(t,x) \right) \\
  J(x,t_f) & = \phi(x)
\end{align}  \cdots (14)
$$ 

# 3. 경로 적분

# Reference

[1] [Kappen, Hilbert J. "Path integrals and symmetry breaking for optimal control theory." Journal of statistical mechanics: theory and experiment 2005.11 (2005): P11011.](https://arxiv.org/abs/physics/0505066)

[2] [Kappen, Hilbert J. "An introduction to stochastic control theory, path integrals and reinforcement learning." AIP conference proceedings. Vol. 887. No. 1. American Institute of Physics, 2007.](https://www.snn.ru.nl/~bertk/kappen_granada2006.pdf)

[3] [G. Williams, P. Drews, B. Goldfain, J. M. Rehg and E. A. Theodorou, "Aggressive driving with model predictive path integral control," 2016 IEEE International Conference on Robotics and Automation (ICRA), Stockholm, Sweden, 2016, pp. 1433-1440, doi: 10.1109/ICRA.2016.7487277. keywords: {Trajectory;Optimal control;Entropy;Vehicles;Prediction algorithms;Q measurement;Stochastic processes},](https://ieeexplore.ieee.org/document/7487277)

[4] [Williams, Grady, et al. "Information theoretic mpc for model-based reinforcement learning." 2017 IEEE international conference on robotics and automation (ICRA). IEEE, 2017.](https://homes.cs.washington.edu/~bboots/files/InformationTheoreticMPC.pdf)

[5] [Williams, Grady, et al. "Information-theoretic model predictive control: Theory and applications to autonomous driving." IEEE Transactions on Robotics 34.6 (2018): 1603-1622.](https://arxiv.org/abs/1707.02342)

