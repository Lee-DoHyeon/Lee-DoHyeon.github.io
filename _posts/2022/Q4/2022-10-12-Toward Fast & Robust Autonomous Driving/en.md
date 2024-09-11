---
title: "Toward Fast and Robust Autonomous Driving"
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
toc_label: "Toward Fast and Robust Autonomous Driving"
category: Meditation
tags: [Optimal Control Theory, Autonomous Driving, Model-Based Control, Information Theory]
lang: en
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

> "We live in a world that is complex, nonlinear, and uncertain. How can we develop strategies to navigate this chaotic environment and ensure our survival? And can we enable robots to learn and discover such strategies on their own?"


<div class="centered-container">
  <figure>
    <iframe src="https://giphy.com/embed/AS4N79Rt53Ss2rdVIg" width="480" height="319" style="" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
    <figcaption>
      Driving on slippery, uneven terrain like a desert, Source: <a href="https://giphy.com/gifs/offroad-monster-energy-canam-AS4N79Rt53Ss2rdVIg">GIPHY</a>
    </figcaption>
  </figure>
</div>

Think about vehicles, robots, or even nuclear power plants. These are all **systems** composed of smaller components like sensors, bolts, nuts, and motors. We expect these systems to perform actions as we desire. Take driving as an example: every morning and evening, we use our eyes and ears to perceive near and distant surroundings, adjusting the pressure on the pedal with our right foot to navigate the road. How can we replicate this behavior in machines or software?


This article aims to summarize the insights gained while studying **Optimal Control Theory** in the context of **Autonomous Driving**, specifically focusing on **Information-Theoretic Model Predictive Control (MPC)**, a popular algorithm in the field of **Model Predictive Control**.


---

# 1. The Origins of Optimal Control Theory

The effort to control a system in the most efficient way has deep roots in the **cybernetics** movement and eventually evolved into what is now known as **Optimal Control Theory (OCT)**. OCT provides a theoretical framework and engineering methodologies to guide systems towards the desired optimal actions. It requires a strong mathematical background as it was founded by two mathematical geniuses: [**Richard E. Bellman**](https://en.wikipedia.org/wiki/Richard_E._Bellman) from the United States and [**Lev Pontryagin**](https://en.wikipedia.org/wiki/Lev_Pontryagin) from the Soviet Union.


## 1.1 Richard Bellman and Lev Pontryagin

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/1.jpg" style="width: 60%; height: auto;">
      <figcaption>
        Richard E. Bellman, American mathematician. Source: Wikipedia.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/2.jpg" style="width: 55%; height: auto;">
      <figcaption>
        Lev Pontryagin, Soviet mathematician. Source: <a href="https://timenote.info/en/Lev-Pontryagin">Timenote</a> 
      </figcaption>
    </figure>
  </div>
</div>

Richard Bellman, famous for his autobiography "[**Eye of the Hurricane**](https://www.amazon.com/Hurricane-Autobiography-Richard-Ernest-Bellman/dp/9971966018)," worked on missile control problems at RAND Corporation in the 1950s. He is the inventor of [**Dynamic Programming**](https://en.wikipedia.org/wiki/Dynamic_programming), a method that simplifies complex problems by breaking them into smaller, recursive problems. Bellman applied this technique to the [**Hamilton-Jacobi Equation**](https://en.wikipedia.org/wiki/Hamilton%E2%80%93Jacobi_equation), which describes the motion of particles in terms of waves. This led to the [**Hamilton-Jacobi-Bellman (HJB) Equation**](https://en.wikipedia.org/wiki/Hamilton%E2%80%93Jacobi%E2%80%93Bellman_equation), commonly referred to as the HJB equation.

On the other hand, Lev Pontryagin, despite being blind, made remarkable contributions across various fields. He is best known for Pontryagin's [**Maximum Principle**](https://en.wikipedia.org/wiki/Pontryagin%27s_maximum_principle), which, like Bellman's approach, derives similar results using rigorous mathematics. His work was later applied to economics by Nobel laureate [**Leonid Kantorovich**](https://ko.wikipedia.org/wiki/%EB%A0%88%EC%98%A4%EB%8B%88%ED%8A%B8_%EC%B9%B8%ED%86%A0%EB%A1%9C%EB%B9%84%EC%B9%98). Pontryagin's approach involved solving optimal control problems using differential equations, which had limitations due to boundary conditions. Bellman's approach, using partial differential equations, was more flexible but still faced challenges like the curse of dimensionality.

## 1.2 Discrete-Time Optimal Control Problems

An optimal control problem consists of three main components: a dynamic system that evolves over time, a control input that affects the system, and a cost function that evaluates the system's performance. Let’s start with a discrete-time dynamic system, where the state variable at time $t$ is denoted as $x_t$ and the control input as $u_t$:

$$
x_{t+1} = f(t, x_t, u_t), \ \  t= 0,1,...,T \cdots (1)
$$

The system incurs a cost or reward $R(t, x_t, u_t)$ at each time step, and the total accumulated cost over a time horizon is given by:

$$
C(x_0, u_{0:T}) = \sum_{t=0}^{T} R(t,x_t,u_t) \cdots (2)
$$

The goal is to find the optimal control $J(t, x_t)$ that minimizes the total cost:

$$
J(t, x_t) = \min_{u_{t:T}} \sum_{s=t}^{T} R(s,x_s,u_s) \cdots (3)
$$

This leads to a recursive relationship known as Bellman’s dynamic programming equation:

$$
\begin{align} 
	\underline{J(t,x_t)} & = \min_{u_{t:T}} \sum_{s=t}^{T} R(s,x_s,u_s) \ by\ definition \\ 
    	& = \min_{u_t}\left( R(t,x_t,u_t) + \min_{u_{t+1:T}} \sum_{s=t+1}^{T} R(s,x_s,u_s) \right) \\ 
      & =\min_{u_t}\left( R(t,x_t,u_t) + J(t+1, x_{t+1}) \right) \\
      & =\min_{u_t}\left( R(t,x_t,u_t) + \underline{J(t+1, f(t,x_t,u_t))} \right) \cdots (4)
\end{align} 
$$

By initializing $J(T+1, x) = 0$, we can work backwards to compute the optimal control.


## 1.3 Continuous-Time Optimal Control Problems

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


<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/Kappen.png" style="width: 30%; height: auto;">
      <figcaption>
        네덜란드의 물리학자 힐버트 카펜(Hilbert J. Kappen), 출처: <a href="https://snn.ru.nl/~bertk/">그의 웹사이트</a>.
      </figcaption>
  </figure>
</div>

기존의 최적 제어 이론은 훌륭한 이론적 프레임워크를 제안하는 데에는 성공했으나, 컴퓨터를 활용해 해답을 구하는 과정이 너무나 오래 걸렸다. 이에 더해, 동역학계 모델 $f$를 역으로 추정하거나 변수 $x$의 참값을 측정하거나 정확한 입력 $u$를 적용하는 데에도 한계가 있었다. 그러던 와중, 네덜란드의 물리학자 힐버트 카펜(Hilbert J. Kappen)은 HJB 방정식에 *잡음 항(Noise Term)을 추가함*으로써 이를 해결하기 시작했다. 그는 네덜란드의 랏바우트 대학교(Radboud University)의 생물물리학과에 속한 물리학 교수로, **기계 학습의 물리적 과정(The Physics of Machine Learning)**에 초점을 맞추어 연구를 수행하고 있다. 그렇다면 여기서 그가 추가한 잡음(Noise)란 무엇인가?

## 2.1 위너 프로세스

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/Norbert_Wiener.png" style="width: 60%; height: auto;">
      <figcaption>
        미국의 수학자 노버트 위너(Norbert Wiener), 출처: 위키피디아.
      </figcaption>
    </figure>
    <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/brownian.gif" style="width: 75%; height: auto;">
    <figcaption>
      브라운 운동. 수학적으로는 위너 프로세스로 표현된다.
    </figcaption>
  </figure>
  </div>
</div>


수학에서 **위너 과정(Wiener Process)**은 미국의 수학자이자 사이버네틱스 운동의 창시자인 **[노버트 위너(Norbert Wiener)](https://en.wikipedia.org/wiki/Norbert_Wiener)**에 의해 발견된 연속 시간 확률 과정(Continuous-Time Stochastic Process)이다. 이는 종종 아인슈타인이 연구했던 물 속 꽃가루의 움직임을 다루는 브라운 운동(Brownian Motion)으로도 표현되는데, 형식적으로는 깊은 관계를 갖는다. 대부분의 자연 현상은 잡음이 포함되어 있으며, 수많은 확률 과정에서도 또한 공통적으로 발견할 수 있다. 기존의 최적 제어 이론은 결정론적인(Deterministic) 가정을 도입하여 확률의 개입을 막았지만, 수많은 실제 문제에서는 확률 과정의 도입이 필요해 보인다. 이 위너 과정이야 말로 수학적으로, 물리적으로 자연스러운 잡음으로 생각하면 된다.


위너 과정의 수학적 정의를 파악해보자. 어떤 확률 과정 $W_t$가 다음의 특징을 만족하면 위너 확률 과정이라고 부른다:
  1. $W_0 = 0$.
  2. 임의의 $t>0$에 대해, 미래의 변화량 $W_{t+u} - W_t, u \leq 0$은 과거의 값들 $s < t$인 $W_s$에 대해 독립이다.
  3. $W_{t+u} - W_t \sim \mathit{N}(0, \nu)$.
  4. $W_t$는 $t$에 대해 연속이다.

미적분과 관련해, 위너 확률 과정의 시간에 대한 변화량 $d\xi$는 다음과 같은 성질을 지닌다. 이 특징은 아인슈타인이 발견한 결론과도 유사하다. 아인슈타인은 브라운 운동에 대한 공식에서, 거리 제곱의 평균이 시간에 비례한다는 결론을 내렸다. 이 결론은 아래의 성질과 일맥상통한다:

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

---

<br>

# 3. 경로 적분 프레임워크

이렇게 구한 sHJB 방정식은 비선형 편미분 방정식이기 때문에 일반해를 구하기 무척 어렵다. 카펜은 근사 해(Approximation Solution)에 대한 시뮬레이션 결과를 얻을 수 있도록 경로 적분의 꼴로 변환하는 전략을 취한다. 일단 이 방정식을 경로 적분 형태로 변형시키려면, 몇가지 가정이 필요하다. 

## 3.1 LQ 문제로 축소  

sHJB 문제를 선형화하려면 먼저 몇가지 가정을 도입해 문제를 축소할 수 있다. 먼저, 동역학계에 대한 제어 입력의 선형화(Linearization)이다. 두번째는 비용에 대한 제어 입력의 이차화(Quadratization)이다. 이 두 가정이 적용된 문제를 **LQ 문제**라고 표현한다. 
  
쉽게 표현해보면, 앞서 정의한 확률적 최적 제어 문제를 다시 생각해보자. 수식 (11)에서 동역학계가 제어 입력에 대해 선형적 관계를 유지한다는 것은 동역학계 $f$를 *(1)제어에 독립적인 부분*과 *(2)제어 입력에 선형적으로 의존하는 부분*으로 분리할 수 있음을 의미한다. 즉:

$$
f(x,u,t) = b(x,t) + Bu
$$

마찬가지로, 제어 입력이 비용에 대해 이차항의 관계를 지닌다는 것은, 수식 (12)에서 보상 항 $R(x,u,t)$를 *(1)제어에 독립적인 부분*과 *(2)제어 입력에 이차적으로 의존하는 부분*으로 분리할 수 있음을 의미한다. 즉:

$$
R(x,u,t) = V(x,t) + \frac{1}{2} u^T R u
$$

따라서 이 가정을 적용하여 확률적 최적 제어 문제를 축소해보면, 다음과 같이 정리할 수 있다.

$$
\begin{align} 
  dx & = \left( b(x,t) + Bu \right)dt + d\xi \cdots (15) \\
  C(t_i, x_i, u(t_i \rightarrow t_f)) & = \biggl< \phi(x(t_f)) + \int_{t_i}^{t_f} dt \left(  V(x(t),t) + \frac{1}{2} u(t)^T R u(t) \right) \biggr>_{x_i}  \cdots (16) \\
\end{align} 
$$

이를 적용해 유사한 방식으로 sHJB 방정식을 유도하면, 다음과 같은 축소된 방정식을 얻을 수 있다:

$$
\begin{align} 
  - \partial_{t} J & = \min_{u} \left( V + \frac{1}{2} u^T R u  + (b + Bu)^{T} \partial_{x} J + \frac{1}{2} \mathrm{Tr} \left( \nu \partial_{x}^2J \right) \right) \\
  J(x,t_f) & = \phi(x)
\end{align}  \cdots (17)
$$ 

롤의 정리(Rolle's Theorem)에 의해 우변이 0이 되도록 만드는 $u$를 찾아 정리하면. 다음과 같이 표현할 수 있다(찾는 과정은 생략한다). 

$$
u=-R^{-1}B^T \partial_{x} J(x,t)
$$

이 최적해의 후보를 수식 (17)의 우변에 대입하면, 다음과 같이 정리할 수 있다.

$$
\underline{- \frac{1}{2} (\partial_{x} J)^T BR^{-1}B^T (\partial_{x} J)} + V + b^{T} \partial_{x} J + \underline{\frac{1}{2} \mathrm{Tr} \left( \nu \partial_{x}^2J \right)}  \cdots (18)
$$

## 3.2 Log 변환

보다 시피, sHJB 방정식 LQ 가정으로 축소했더라도 $J$에 대한 이계 미분 항이 남아 있어 아직은 비선형 방정식이다(수식 (18)의 밑줄 친 항을 보라). 이때 이 방정식을 선형화할 수 있도록 로그 변환을 통해 수식을 선형화해보자. 즉 기존의 $J$ 대신 새로운 $\psi$를 도입하는 것이다. 이때 비례 상수는 미래의 수식 전개를 고려하여 $-\lambda$로 설정한다. 즉:

$$
J(x,t) = - \lambda \log \psi(x,t) \cdots (19)
$$

이를 수식 (18)의 밑줄 친 이차항에 적용하면, 다음과 같이 수식을 변형할 수 있다. 

$$
\begin{align}
  - \frac{1}{2} (\partial_{x} J)^T BR^{-1}B^T (\partial_{x} J) + \frac{1}{2} \mathrm{Tr} \left( \nu \partial_{x}^2J \right) & = \underline{- \frac{\lambda^2}{2 \psi^2} \sum_{i, j} (\partial_x \psi)_i (BR^{-1}B^T)_{i,j}(\partial_x \psi)_j}\\
  & \quad +\underline{\frac{\lambda^2}{2 \psi^2}  \sum_{i, j} \nu_{i,j} (\partial_x \psi)_i (\partial_x \psi)_j} \\
  & \quad -\frac{\lambda}{2 \psi} \sum_{i,j} \nu_{i,j} \frac{\partial^2 \psi}{\partial x_i \partial x_j}.
\end{align}
$$

이 식이 일차식이 되려면 밑줄 친 첫번째와 두번째 항의 합이 0이 되어야 한다. 그에 따른 필요 충분 조건은 **적절한 비례 상수 $\lambda$의 존재성**으로 해석할 수 있다. 즉, 우리가 어떤 비례 상수를 갖는 로그 변환을 할 지 결정하면 된다는 것이다. 그 적절함의 기준을 형식적으로 유도해 작성해내면 다음과 같다.

$$
\exists \ a\ scalar\ \lambda \mid \nu = \lambda B R^{-1} B^T \cdots (20)
$$

## 3.3 Kolmogorov 역향 방정식

만약 수식 (20)을 만족하는 적절한 비례상수 $\lambda$를 선택하여 로그 변환을 취했다고 가정하자. 그러면 수식 (18)은 선형 방정식으로 전체적인 기존의 sHJB 방정식은 아래와 같은 형태가 된다. 아래의 형태는 과거 소비에트 연방의 수학자 [안드레이 콜모고로프](https://en.wikipedia.org/wiki/Andrey_Kolmogorov)가 개발한 편미분 방정식으로, **[콜모고로프 역향 방정식(Kolmogorov Backward Equation)](https://en.wikipedia.org/wiki/Kolmogorov_backward_equations_(diffusion))**이라고도 불린다. 일반적으로 이 방정식은 연속 시간, 연속 상태의 [마코프 과정](https://en.wikipedia.org/wiki/Markov_process)에 대한 연구에서 파생되었다. 시스템의 현재 상태에 대한 정보(확률 분포)로부터 미래 상태에 대한 정보(확률 분포)를 파악할 때 유용하다. 

$$
\begin{align}
  - \partial_t \psi & = H\psi,\ where\ an\ operator\ H = \left( \frac{V}{\lambda} + b^T\nabla + \frac{1}{2} \nu \nabla^2 \right)
\end{align} \cdots (21)
$$

한편, 미국의 이론 물리학자인 [리처드 파인만](https://en.wikipedia.org/wiki/Richard_Feynman)과 수학자인 [마크 칵](https://en.wikipedia.org/wiki/Mark_Kac)은 원자 폭탄과 관련된 맨해튼 프로젝트에서 중성자의 무작위적 궤적을 계산하기 위해 **[파인만-칵 공식(Feynman-Kac Formula)](https://en.wikipedia.org/wiki/Feynman%E2%80%93Kac_formula)**을 개발하였다. 이 공식을 활용하면 확률 과정에 따른 무작위적인 궤적을 시뮬레이션함으로써, 수식 (21)과 같은 편미분 방정식을 풀 수 있게 만들어준다. 공식에 대해 자세히 다루진 않겠지만, 이를 적용하면 다음과 같이 수식을 전개할 수 있다:

$$
J(x,t) = -\lambda \log \int [dx]_x \exp{ - \frac{1}{\lambda} S(x(t \rightarrow t_f))} + C \cdots (22)
$$

이 때, 수식 (22)에서 등장하는 $S$는 *(1)최종 시스템 상태에 대한 제약 조건*과 *(2)시스템의 시간에 따른 궤적의 비용*으로 해석할 수 있으며, 구체적 수식은 다음과 같다:

$$
\begin{align}
  S(x(t \rightarrow t_f)) & := \phi(x(t_f)) + \underline{S_{path}(x(t \rightarrow t_f))} \\
  & = \phi(x(t_f)) + \underline{\int_{t}^{t_f} d\tau \left( \frac{1}{2} \left( \frac{dx(\tau)}{d\tau} - b(x(\tau), \tau) \right)^T R \left( \frac{dx(\tau)}{d\tau} - b(x(\tau), \tau) \right) + V(x(\tau), \tau) \right)}
\end{align} \cdots (23)
$$

<br>

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/Pi_monte_carlo_all.gif" style="width: 70%; height: auto;">
      <figcaption>
        MC 샘플링 기법을 활용해 정확한 원주율 값을 구하는 과정, 출처: 위키피디아.
      </figcaption>
  </figure>
</div>

위 경로 적분의 형태는 통계학의 샘플링(Sampling) 기법을 활용해 계산할 수 있다. 카펜은 그의 논문에서 간단한 **[마코프 체인 샘플링(MC Sampling)](https://en.wikipedia.org/wiki/Monte_Carlo_method)** 기법을 통해 시뮬레이션을 수행한다.

## 3.4 열역학 및 강화학습과의 관계



수식 (22)는 사실 정보 이론에서 자주 등장하는 **자유 에너지(Free Energy)**의 형태와 아주 유사하다. 수식에 등장하는 log 안의 적분 꼴은 통계 역학에서 등장하는 **[분배 함수(Partition Function)](https://en.wikipedia.org/wiki/Partition_function_(statistical_mechanics))**이다. 전체적으로는 분배 함수에 로그가 취해진 꼴로, **[자유 에너지](https://en.wikipedia.org/wiki/Thermodynamic_free_energy)**로 해석할 수 있다. 


<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/Reinforcement_learning_diagram.svg.png" style="width: 70%; height: auto;">
      <figcaption>
        강화학습 프레임워크, 출처: 위키피디아.
      </figcaption>
  </figure>
</div>

또한, 최근 각광 받는 **[강화학습(Reinforcement Learning )](https://en.wikipedia.org/wiki/Reinforcement_learning)**과도 관련성을 지니고 있다. 강화학습은 정상(Stationary) 상태의 환경에서 할인된 미래 보상(Discounted future reward)에 대해 최적 제어 문제라고 볼 수 있다. 다만, 최적 제어 이론은 유한한 미래 상황을 고려하는 반면, 강화학습은 무한한 미래를 다루는 경향이 있다. 또 제어 입력과 비용에 대한 용어도 다른데, 강화학습은 최적 정책(Policy)과 가치(Value)라는 개념을 사용한다. 최적 제어 이론은 효과적인 제어기(Controller)를 개발하고자 하는 반면, 강화학습은 에이전트(Agent)를 개발하는 것을 목표로 한다.

---

<br>

# 4. 정보 이론 프레임워크

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/evangelos-theodorou-300x300.jpg" style="width: 70%; height: auto;">
      <figcaption>
        미국 조지아공과대학교 소속의 기계공학과 교수인 에반겔로스 테오도루, 출처: <a href="https://research.gatech.edu/evangelos-theodorou">조지아텍</a>.
      </figcaption>
  </figure>
</div>

힐버트 카펜은 경로 적분 프레임워크를 개발하여, 최적 제어를 구하는 최적화 문제에 대한 효과적 방법론을 제안했다. 그의 시도는 고전적인 최적 제어 이론에서 시작해, 현대적인 과학적 계산(Scientific Computing)에 맞게 진화했다. 이러한 시도와 정반대로, 조지아 공과 대학교의 에반겔로스 테오도루는 정보이론에서 역 방향으로 접근한다. 그는 정보이론의 변분 자유 에너지로부터 HJB 방정식을 유도해낸다. 이를 이해하려면, 확률과 정보 이론에 대한 기초 지식부터 알 필요가 있다.


## 4.1 자유 에너지

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2022/Q4/2022-10-12-Toward Fast & Robust Autonomous Driving/Shannon.jpg" style="width: 60%; height: auto;">
      <figcaption>
        정보 이론의 아버지로 불리는 미국의 수학자 클로드 섀넌, 출처: 위키피디아.
      </figcaption>
  </figure>
</div>

자유 에너지를 설명하기 전에 먼저, **정보**에 대해 소개할 필요가 있다. **정보 이론**은 1940년대, 미국의 수학자 클로드 섀넌(Claude Elwood Shannon)이 개발한 이론으로 주어진 (확률) 변수에 대한 **불확실성(Uncertatinty)**을 표현하기 위해 개발되었다. 그에 따르면 어떤 확률 변수 $X$와 그에 따른 확률 분포 $P_X(X=x)$가 주어지면, 특정 사건에 대한 **자기 정보(Self-Information)**를 다음과 같이 $- \log$를 취해 표현할 수 있고, 그 형태가 고유하다. 이는 확률이 높은 사건일 수록 불확실성이 줄고, 정보가 많다고 느끼는 직관과도 잘 맞는다. 이때 전체 분포를 바탕으로 각 사건들에 대한 정보의 평균을 취한 것을 **엔트로피**로 정의한다. 해당 확률 *변수가 지닌 평균적인 불확실성*인 셈이다.

$$
\begin{align}
  I(X=x) & = - \log P_X(X=x) \cdots self-information\ of\ x \\
  \mathcal{E}(X) & = \mathbb{E}_{x \sim P_X} \left[ - \log P_X(X=x) \right] \cdots entropy\ of\ X
\end{align}
$$  


이때, 자유에너지는 주어진 임의의 확률 분포 $\mathbb{P}$와 이를 통해 측정 가능한(measurable) 함수 $J$, 음의 실수 파라미터인 $\rho \in \mathbb{R}^{-}$에 의해 다음과 같이 정의한다. 즉, 확률 분포 $\mathbb{P}$의 관점에서 측정 가능한(measurable) 함수 $J$의 자유 에너지는 다음과 같다:

$$
\mathcal{F} = \log_{e} \int \exp \left( \rho \mathcal{J}(x) \right) \mathbb{d}\mathbb{P}  \cdots (24)
$$

이때, 실제 확률 변수가 따르는 분포 $\mathbb{P}$를 알 수 없으므로, 변분 추론(Variational Inference)의 맥락에서 $\mathbb{Q}$를 도입해보자. 그러면, 두 분포의 차이를 쿨백-라이불러 발산(Kullback-Leibler Divergence)으로 표현할 수 있다:

$$
\begin{align}
  \mathbb{KL(Q||P)} & = \mathbb{E}_{X \sim Q}\left[ \log{\mathbb{Q}(X)} - \log{\mathbb{P}(X)}\right] \\
  & = \int \log_{e} \frac{\mathbb{dQ}}{\mathbb{dP}} \mathbb{dQ}
\end{align}
$$  

이제 자유 에너지에 쿨백-라이불러 발산을 도입하면, 르장드르 변환(Legendre Transform)에 의해 아래와 같은 부등식을 얻을 수 있다. 이 때 등호 조건은 아래와 같다:

$$
\begin{align}
  - \frac{1}{|\rho|} \log_{e} \mathbb{E_P} \left[ \exp(-|\rho|\mathcal{J}) \right] & \leq \left[ \mathbb{E_Q}(\mathcal{J}) + {|\rho|}^{-1} \mathbb{KL(Q||P)} \right] \\
   & = \inf_{\mathbb{dQ}} \left[ \mathbb{E_Q}(\mathcal{J}) + {|\rho|}^{-1} \mathbb{KL(Q||P)} \right],\ when\ \mathbb{dQ^*} = \frac{\exp(- |\rho| \mathcal{J}) \mathbb{dP}}{\int {\exp(- |\rho| \mathcal{J}) \mathbb{dP}} }
\end{align} \cdots (25)
$$  

## 4.2 최적 제어 문제

앞서 소개한 확률적 최적 제어 문제와 경로 적분 프레임워크의 결론을 참고하여 풀고자 하는 문제로 형식화해보자. 먼저, 비용함수 $\mathcal{J}$를 최종 상태 $t_N$에만 의존하는 비용 $\phi(\mathbb{x}(t_N), t_N)$와 특정 시간과 상태에서의 비용 $q(\mathbb{x}, \tau)$를 적분한 궤적의 운영 비용 $\int_{t}^{t_N} q(\mathbb{x}, \tau) \mathbb{d}\tau$의 합으로 정의한다. 이때, 자유 에너지 함수(Free Energy Function)를 임의의 상수 $\nu \in \mathbb{R}^{< 0}$를 도입해 지수 평균의 log를 취한 형태로 정의한다. 여기서, $\rho > 0$은 리스크 회피(Risk Sensitive)를, $\rho < 0$은 리스크 선호(Risk Seeking)을 유도한다.

$$
\begin{align} 
  \mathcal{J} & = \mathcal{J}(\mathbb{x}(\cdot), t) = \phi(\mathbb{x}(t_N), t_N) + \int_{t}^{t_N} q(\mathbb{x}, \tau) \mathbb{d}\tau \cdots (26)\\
  \xi(\mathbb{x}, t) & = \frac{1}{\rho} \log_e \mathbb{E_P} \biggl[ \exp \left( \rho \mathcal{J}(\mathbb{x}, t) \biggr) \right] \cdots (27)
\end{align} 
$$

한편, 이제 시스템에 대한 내용을 도입해 보자. 우리가 제어 입력을 통해 관찰가능한 시스템의 분포를 $\mathbb{Q}$, 아무런 제어 없이 관찰가능한 시스템의 분포를 $\mathbb{P}$라고 해보자. 이때, $\mathbb{w}$는 브라운 노이즈(Brownian Noise) 항이다.

$$
\begin{align} 
  \mathbb{P}^{\mathbf{Controlled}}: \mathbb{dx} & = \mathbf{F} \mathbb{(x,u)} \mathbb{d}t + \mathbf{C} \mathbb{(x)} \mathbb{dw}(t) \\
  \mathbb{Q}^{\mathbf{Uncontrolled}}: \mathbb{dx} & = \mathbf{A}\mathbb{(x)} \mathbb{d}t + \mathbf{C} \mathbb{(x)} \mathbb{dw}(t)
\end{align} \cdots (29)
$$

먼저, $\delta F$를 다음과 같이 정의하자:

$$
\delta \mathbf{F} \mathbb{(x,u)} = \mathbf{F} \mathbb{(x,u)}  - \mathbf{A} \mathbb{(x)}  = \mathbf{F} \mathbb{(x,u)} - \mathbf{F} \mathbb{(x,0)},\ \forall x, u
$$

그러면, $\Sigma_\mathbf{C} = \mathbf{C}\mathbb{(x)}\mathbf{C}\mathbb{(x)}^T$라고 정의했을 때 두 확률 변수의 [라돈-니코딤 도함수(Radon-Nikodym Derivative)](https://en.wikipedia.org/wiki/Radon%E2%80%93Nikodym_theorem#:~:text=.-,Radon%E2%80%93Nikodym%20derivative,-%5Bedit%5D)는 다음과 같이 정의할 수 있다:

$$
\mathbb{\frac{dQ}{dP}} = \exp \biggl[ \int_{t_0}^{t_N} \left( \delta \mathbf{F}^T\mathbf{C}\mathbb{(x)}^{-1}\mathbb{dw(t)} + \frac{1}{2}\delta \mathbf{F}^T\mathbb{\Sigma}_\mathbf{C}^{-1}\delta \mathbf{F} \delta t \right) \biggr] \cdots (30)
$$

앞서 소개한 수식 (25)의 르장드르 부등식과 등호 조건에 수식 (30)의 라돈-니코딤 도함수를 적용해보자. 그러면 이 등호식은 $\mathbb{Q}$의 관점에서 상태에 대한 비용인 상태 비용(State Cost)과, 실제 물리적 과정에 따른 $\mathbb{P}$와의 쿨백-라이불러 발산(Kullback-Leibler Divergence)을 의미하는 정보 비용(Information Cost)의 두 항으로 쪼개어 나타낼 수 있다. 더욱이 이 두 비용의 상충 관계(Trad-Off) 중에서 이 둘 모두를 최소화하도록 설계되었다는 점을 확인할 수 있다.

$$
\begin{align}
  - \frac{1}{|\rho|} \log_{e} \mathbb{E_P} \left[ \exp(-|\rho|\mathcal{J}) \right] & \leq \underbrace{\mathbb{E_Q}\left[(\mathcal{J})\right]}_{State\ Cost} + \underbrace{\mathbb{E_Q}\left[\frac{1}{2|\rho|} \delta \mathbf{F}^T\mathbb{\Sigma}_\mathbf{C}^{-1}\delta \mathbf{F} \delta t \right]}_{Information\ Cost} \\
   & = \mathbb{E_Q}\left[(\mathcal{J})\right] + \mathbb{E_Q}\left[\frac{1}{2|\rho|} \delta \mathbf{F}^T\mathbb{\Sigma}_\mathbf{C}^{-1}\delta \mathbf{F} \delta t \right],\ when\ \mathbb{dQ^*} = \frac{\exp(- |\rho| \mathcal{J}) \mathbb{dP}}{\int {\exp(- |\rho| \mathcal{J}) \mathbb{dP}} }
\end{align} \cdots (31)
$$  

## 4.3 sHJB 방정식 유도

수식 (29)에서 제어 동역학이 입력에 대해 선형적이라는 [어파인(Affine Transformation)](https://en.wikipedia.org/wiki/Affine_transformation) 가정을 도입하자.

$$
\begin{align} 
  \mathbb{P}^{\mathbf{Controlled}}: \mathbb{dx} & = \mathbf{f} \mathbb{(x)} \mathbb{d}t + \frac{1}{\sqrt{|\rho|}}\mathcal{B} \mathbb{(x)} \mathbb{dw}^{(0)}(t) \\
  \mathbb{Q}^{\mathbf{Uncontrolled}}: \mathbb{dx} & = \mathbf{f} \mathbb{(x)} \mathbb{d}t + \mathcal{B} \mathbb{(x)} \biggl( \mathbf{u} \mathbb{d}t + \frac{1}{\sqrt{|\rho|}}\mathbb{dw}^{(1)}(t) \biggr)
\end{align} \cdots (32)
$$

그러면, 자유에너지에 적용된 르장드르 부등식은 다음과 같아진다.

$$
\begin{align} 
  \xi(\mathbb{x}) & = - \frac{1}{\rho} \log_e \mathbb{E_P} \biggl[ \exp \left( - |\rho| \mathcal{J}(\mathbb{x}) \biggr) \right] \\
  & \leq \mathbb{E_P} \biggl[ \mathcal{J}(\mathbb{x}) + \frac{1}{2} \int_{t_i}^{t_N} \mathbf{u}^T\mathbf{u} \mathbb{d}t \biggr]
\end{align}  \cdots (33)
$$

이 때, 다음과 같이 새로운 변수 $\Phi$를 도입해보자.

$$
\mathbf{\Phi}(\mathbb{x}, t) = \mathbb{E_P}\left( \exp (\rho \mathcal{J}(\mathbb{x})) \right)  \cdots (34)
$$

그러면, **[파인만-칵 공식(Feynman-Kac Formula)](https://en.wikipedia.org/wiki/Feynman%E2%80%93Kac_formula)**에 의해, 이 함수는 **[콜모고로프 역향 방정식(Kolmogorov Backward Equation)](https://en.wikipedia.org/wiki/Kolmogorov_backward_equations_(diffusion))**을 따른다. 더욱이 다음의 방정식이 참이다. 

$$
- \partial_t \mathbf{\Phi} = \rho q_o \mathbf{\Phi} + \mathbf{f}^T(\nabla_\mathbb{x} \mathbf{\Phi}) + \frac{1}{2|\rho|} \mathrm{Tr} \biggl( (\nabla_{\mathbb{xx}} \mathbf{\Phi}) \mathcal{B} \mathcal{B}^T \biggr) \cdots (35)
$$

앞서 경로 적분 프레임워크에서 활용한 Log 변환과 유사하게 $\mathbf{\xi}(\mathbb{x}) = \frac{1}{\rho} \log \mathbf{\Phi}(\mathbb{x}, t)$를 적용해 수식을 적용하면, 다음과 같은 식이 나온다. 이때, $\rho$의 양수/음수 여부에 따라 동순으로 다음과 같이 정리할 수 있다. 

$$
- \partial_t \mathbf{\xi} = q_0 + (\nabla_\mathbb{x}\mathbf{\xi})^T \pm \frac{1}{2} (\nabla_\mathbb{x} \mathbf{\xi})^T \mathcal{B}\mathcal{B}^T(\nabla_\mathbb{x} \mathbf{\xi}) + \frac{1}{2|\rho|} \mathrm{Tr} \biggl( (\nabla_{\mathbb{xx}} \mathbf{\xi}) \mathcal{B} \mathcal{B}^T \biggr) \cdots (36)
$$

그런데, 이 방정식은 바로 sHJB 방정식이다. 이로써, 어떠한 최적성의 원리(Principle of Optimality)를 도입하지 않고도 sHJB을 유도해낼 수 있게 되었다!

---

이로써, 우리는 복잡한 최적 제어의 문제가 어떻게 확률적 추론의 문제와 관련되는지 수학적으로 살펴 보았다. 1에서는 고전적인 결정론적 최적 제어 문제와 HJB 방정식, 동적 프로그래밍을 활용한 계산 방법을, 2에서는 확률적 최적 제어 문제의 형식화와 sHJB 방정식을 소개했다. 3에서는 확률적 최적 제어 문제를 콜모고로프 역향 방정식으로의 유도한 이후 파인만-칵 공식을 활용한 샘플링 기반의 계산 방법을, 4에서는 확률적 추론의 관점에서 자유 에너지의 개념과 그것의 최소화를 통해 최적성 원리의 가정 없이 sHJB 방정식을 유도해냈다. 바로 이 주제를 통해, 미분 방정식의 재귀적 연산이 확률적 추론과 순방향 샘플링과 연결되는 순간을 포착할 수 있었다.

# Reference

[1] [Kappen, Hilbert J. "Path integrals and symmetry breaking for optimal control theory." Journal of statistical mechanics: theory and experiment 2005.11 (2005): P11011.](https://arxiv.org/abs/physics/0505066)

[2] [Kappen, Hilbert J. "An introduction to stochastic control theory, path integrals and reinforcement learning." AIP conference proceedings. Vol. 887. No. 1. American Institute of Physics, 2007.](https://www.snn.ru.nl/~bertk/kappen_granada2006.pdf)

[3] [Theodorou, Evangelos, D. Krishnamurthy, and Emo Todorov. "From information theoretic dualities to path integral and kullback-leibler control: Continuous and discrete time formulations." The sixteenth yale workshop on adaptive and learning systems. Vol. 95. 2013.](https://homes.cs.washington.edu/~todorov/papers/TheodorouYale13.pdf)

[4] [G. Williams, P. Drews, B. Goldfain, J. M. Rehg and E. A. Theodorou, "Aggressive driving with model predictive path integral control," 2016 IEEE International Conference on Robotics and Automation (ICRA), Stockholm, Sweden, 2016, pp. 1433-1440, doi: 10.1109/ICRA.2016.7487277. keywords: {Trajectory;Optimal control;Entropy;Vehicles;Prediction algorithms;Q measurement;Stochastic processes},](https://ieeexplore.ieee.org/document/7487277)

[5] [Williams, Grady, et al. "Information theoretic mpc for model-based reinforcement learning." 2017 IEEE international conference on robotics and automation (ICRA). IEEE, 2017.](https://homes.cs.washington.edu/~bboots/files/InformationTheoreticMPC.pdf)

[6] [Williams, Grady, et al. "Information-theoretic model predictive control: Theory and applications to autonomous driving." IEEE Transactions on Robotics 34.6 (2018): 1603-1622.](https://arxiv.org/abs/1707.02342)

