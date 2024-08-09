---
title: 의식에 대한 능동추론적 관점
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
toc_label: "의식에 대한 능동추론적 관점"
category: Motivation
tags: [의식, 능동추론, 신경과학, 논문]
lang: kr
image: assets/images/posts/2023/Q2/2023-05-14-AIF and Consciousness/consciousness_classification.png
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
</style>


> "최근들어 Karl Friston의 능동추론이 다양한 뇌의 기능을 설명하고 있다. 능동추론의 프레임워크를 잘 활용하여 의식을 설명할 수도 있지 않을까?"


> 본 글은 Lucia Melloni 등의 "Active Inference As a Computational Framework for Consciousness"을 읽고 생각을 정리하는 글입니다.

# I. 의식의 이론들과 설명 문제

**의식의 수수께끼**

1990년대 Crick과 Koch는 의식의 신경 상관물(Neural Correlates of Consciousness; NCC)를 활용하여 의식을 연구하고자 한다. NCC란 특정 의식 경험을 가능하게 하는 최소한의 필수 신경 메커니즘을 의미한다. 그러나, NCC들의 함축적 의미나 연구결과에 대해서는 거의 합의된 바가 없다. 이러한 이유로 저자는 의식에 대한 통일된 설명이 부족하다는 "설명 문제Explanandulum Problem"를 지적한다.

의식Consciousness은 크게 Arousal/Wakefulness과 같은 State에 대한 개념과, Awareness에 대한 Content에 대한 개념으로 분류된다(아래 참고). 전자의 경우, 연구를 위해 fMRI, M/EEG, ECoG 등과 같은 장비를 활용해 연구해왔다. 후자의 경우, 개인이 경험하는 바로 그 주관적 경험에 대한 내용인 현상학적 의식(Phenomenal Consciousness)와, 고차 인지 기능을 가능하게 하는 정보 처리 프로세스에 대한 내용인 접근 의식(Access Consciousness)로 구분된다. 

<div class="centered-container">
  <figure>
    <img src = "/assets/images/posts/2023/Q2/2023-05-14-AIF and Consciousness/consciousness_classification.png" style="width: 80%; height: auto;">
    <figcaption>
      Oversimplified illustration of the two major dimensions of consciousness: the level of consciousness (i.e., arousal or wakefulness) and the content of consciousness (i.e., awareness or experience).
    </figcaption>
  </figure>
</div>

1. **State** of Consciousness: Arousal/Wakefulness
   - A temporally extended state where having a subjective experience is possible or not.
2. **Content** of Consciousness: Awareness
    1. **Phenomenal** consciousness:
      - Subjective qualities of conscious experience
    2. **Access** consciousness:
      - Processes that enable specific information for higher level cognition 

현상학적 의식은 바로 그 질적인 성질인 Qualia를 물리적 대상/속성으로 환원할 수 있는지에 따라 David Chalmers의 [의식의 어려운 문제(The Hard Problem)](https://en.wikipedia.org/wiki/Hard_problem_of_consciousness)와 같은 논의가 이루어지고 있다. 한편, Giulio Tononi의 [통합정보이론(Integrated Information Theory; IIT)](https://en.wikipedia.org/wiki/Integrated_information_theory)에서는 현상학적 의식을 설명하기 위헤, 거시적 규모의 동역학을 연구하고 있다. 접근 의식의 경우, 피실험자의 내적 경험에 대한 보고 내용이나 특정 인지 기능의 발현을 유도하는 자극을 제시함으로써 연구를 수행하고 있다고 한다.

> "이처럼 의식 연구에는 질적으로 구분되는 다양한 연구 패러다임이 혼재되어 있다. 각각의 연구 패러다임마다 주목하고 있는 의식에 대한 설명의 대상이 다르고, 그에 따라 연구의 방법론도 선호하는 것으로 선택하게 된다. 또한 의식에 대해 전체적인 관점을 취할 것인지, 아니면 세부 기능으로 분류하고 다시 통합하여 볼 것인지도 통일된 바가 없다. 이러한 상황에서 능동 추론이 좋은 계산적 관점을 제공할 수 있지 않을까? 이러한 혼란을 전부 converge시킬 수 있지 않을까?"

---

# II. 프로세스 이론을 만들기 위한 프레임워크로써 능동추론

**자유 에너지 원리(Free Energy Principle)**은 "생존을 위해 환경에 적응하는 모든 생물학적 에이전트는 장기적인 surprise를 최소화하고자 한다"는 원리이다. 단순한 이 원리는 공리적이고, 어찌보면 자명하고, 반증불가능하다는 점에서 과학적 이론(Positive/Descriptive Theory; 실증주의적 이론)으로 간주할 수 없다. 대신, 일종의 규범적 이론(Normative Theory)으로 간주할 수 있다. 규범적 이론은 실증주의적 이론과 달리 사실과 경험 가능한 대상만을 다루지 않으며, 가치를 부여하여 주장하는 이론이다.



**예측 프로세싱(Predictive Processing)**은 "우리의 두뇌가 Bayesian Inference의 메커니즘을 활용하여 경험에 기반한 세상에 대한 추론을 바탕으로 surprise를 최소화한다"는 가설을 기반으로 한다. 이때 예측 오차(Prediction Error)는 앞서 이야기한 자유에너지로 해석할 수 있는데, 우리의 두뇌가 다양한 계층적 층위를 통해 이러한 예측 오차를 최소화하도록 설계되어 있다고 간주한다. 이때, 이러한 예측 오차를 줄이기 위해 (1)관측결과를 바탕으로 세상에 대해 추론하는 <u>지각Perception</u>과, (2)접하게 될 가능성을 높이는 샘플링 혹은 <u>행동Action</u>을 수행할 수 있다.



**능동 추론(Active Inference)**은, 예측 프로세싱의 관점에서, 현재 뿐만 아니라 과거와 미래에 대해서도 이야기한다. 구체적으로, 단순히 surprise가 아닌 그것의 기댓값Expectation을 최소화한다는 것이다. 이러한 최소화는 (1)도움이 되는 실천적인(pragmatic) 행동을 수행하거나; <u>실행Exploitation</u>, (2)탐색과 같은 인식론적인(epistemic) 행동을 수행함으로써; <u>탐색Exploration</u> 이루어진다. 이러한 과정은 belief의 정확성과 신뢰도를 추정하는 과정으로도 간주할 수 있다.

---

# III. 의식에 대한 능동추론의 설명

예측 코딩(Predictive Coding)의 관점에서, 의식의 부분적 기능에 대한 설명은 [Anil Seth(2012)(의식의 현상학적 성질)](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2011.00395/full)이나 [Mateusz Wozniak(2018)(자아)](https://pubmed.ncbi.nlm.nih.gov/30233474/)에서 확인할 수 있으며, 생략하도록 한다.

능동추론의 창시자인 Karl Friston은 의식이 어떤 대상(thing)이 아닌, 추론 과정(inferential process)으로 간주한다. 물론 모든 추론 과정이 의식적인 것은 아니다. 오로지 **(1)시간적으로 두텁고(Temporal Thickness), (2)반사실적인 깊이가 깊은(Counterfactual Depth) 심층 생성 모형의 추론**만이 의식적이라고 주장한다. 그에 따르면, 의식은 켜지고 꺼지는 이진적 상태로 구성된 것이 아닌, 스펙트럼처럼 연속적인(graded; spectral) 현상이다.

의식의 내용에 관해서는, 각 계층의 단계에서 추론된 결과에 의한 최대 사후 확률이라는 가설을 세운다. 몇몇의 학자들은 사후 확률 계층의 중간 부분이라고도 제안한다. 아직까지도 의식의 내용과 관련해서는 다양한 의견이 대립하고 있는 상황이다. 그럼에도, 의식의 내용이 추론된 상태라는 것에는 동의한다.

현상학적 성질에 대한 설명의 경우, 고차적인 프로세스의 경우 추상적이고 오랜시간 유지되는 반면, 저차원적인 raw 데이터는 짧은 시간 동안만 유지된다. 이러한 시간적 차이가 전형적인 감각적 경험이나 메타 인지, 주의집중, 신뢰도 추정 등의 원리를 설명할 수 있지 않을까 기대하고 있다. 

---

# IV. 의식의 계산적 프레임워크로써 능동추론

의식 현상을 설명하기 위한 계산적 모형을 만드는 데에 어려움 크게 3가지이다: (1)의식 연구의 타겟이 아직 논란의 중심에 있으며, 각 연구 패러다임마다 상이하다. (2)의식은 오직 1인칭의 관점에서만 접근가능하다는 주관적 본성을 지닌다. (3)신경과학적, 행동적 지표와 관련해 연구결과가 너무 다양하다. 이러한 의식의 주관적 경험에 대한 통합적인 본성 때문에, 아직까지 능동추론을 활용한 모형이 존재하지 않는다. 
> 어떻게 능동추론이 설명의 다양성 문제를 해결하고 통합적인 이론을 제안할 수 있도록 할 수 있을까?

한편, 완벽한 역학적 모형은 해당 현상을 생성하는 데에 모든 인과적으로 관계된 대상들을 특정할 수 있어야 한다. 때문에, 실제 실험 데이터의 시뮬레이션을 통해 검증가능해야 한다. 이때. 다양한 수학/통계적 방법론적 관행을 적용해 모델의 관련성을 확인할 필요가 있다. 즉, 모형Model을 검증하기 위해 (1)실제 실험 데이터Empirical Data, (2)방법론적 관행Practice을 적절히 활용해야 한다.

---

# V. 이후 해야할 일들

능동추론으로 의식의 내용을 설명하려는 계산 모형들은 아직 초창기에 있다. 이러한 모형들은 실제 데이터를 통해 검증될 필요가 있다. 최근 Maxwell Ramstead에 의해 현상학적 데이터와 생성모형을 연결하려는 **계산 현상학적(Computational Neuro-phenomenology)** 시도가 이루어지고 있다.

---

Karl Friston은 2017, AEON에 "The Mathematics of Mind-Time"이라는 제목의 칼럼을 작성한 이후 의식에 대해 줄곧 관심을 갖고 있는 것 같다. 이후, Mark Solms와 같은 Neuropsychoanalyst와 함께 position paper를 작성하거나, 자신의 제자인 Maxwell Ramstead에게 관련 연구를 지도하고 있는 것 같다. 의식이라는 개념이 워낙 정의되는 방식이 철학적 관점에서도 다양한 만큼, 이런 식으로 한가지 프레임워크에서 언어와 개념을 정립하고 담론을 깔끔하게 구성한다는 점에서 학계에서 기념비적인 사건이 될 수 있지 않을까 생각한다.



본 논문을 읽으며, Bayesian Brain Hypothesis에서 시작한 Active Inference가 어떻게 의식을 설명하려고 노력하는지 확인할 수 있었다. 아직 구체적으로 제안된 모형이 없다는 점에서 굉장히 도전적인 분야인 것 같다. 이러한 논의를 구체적으로 수행하고 결과를 어떻게 해석할 수 있을지 기대된다.



한편, 이러한 논의 이전에 Connectionism이 정말로 유의미한지 파악할 필요가 있지 않을까 싶다. 정보적으로 homomorphic한 계산 과정이 정말 Physical 관점에서 의식이나 지적인 현상을 구현할 수 있을지 의문이다. 정말 다양한 질문이 떠오르는 좋은 가이드인 것 같다. 참조된 논문들을 잘 살펴서 읽어봐야겠다.

### References

[1] [Vilas, M. G., Auksztulewicz, R., & Melloni, L. (2021). Active Inference as a Computational Framework for Consciousness. Review of Philosophy and Psychology, 13(4), 859–878. https://doi.org/10.1007/s13164-021-00579-w ](https://psycnet.apa.org/record/2021-75550-001)

[2] [Adapted from Laureys S (2005) The neural correlate of (un)awareness: Lessons from the vegetative state. Trends in Cognitive Sciences 9: 556–559.](https://pubmed.ncbi.nlm.nih.gov/16271507/)