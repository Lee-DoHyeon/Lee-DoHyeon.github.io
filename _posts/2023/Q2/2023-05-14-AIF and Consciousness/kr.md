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
header:
  teaser: "/assets/images/posts/2023/Q2/2023-05-14-AIF and Consciousness/consciousness_classification.png"
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

> "최근 Karl Friston의 능동추론이 다양한 뇌의 기능을 설명하는 데 사용되고 있다. 이 프레임워크를 통해 의식을 설명할 수 있지 않을까?"

> 이 글은 Lucia Melloni 등의 "Active Inference As a Computational Framework for Consciousness"를 읽고 생각을 정리한 것입니다.

# I. 의식의 이론과 설명의 문제

**의식의 수수께끼**

1990년대 Crick과 Koch는 의식의 신경 상관물(Neural Correlates of Consciousness; NCC)을 활용해 의식을 연구하고자 했다. NCC는 특정 의식 경험을 가능하게 하는 최소한의 필수 신경 메커니즘을 의미한다. 그러나, NCC의 의미나 연구 결과에 대해 합의된 바는 거의 없다. 저자는 이를 '설명 문제(Explanandum Problem)'로 지적하며, 의식에 대한 통일된 설명이 부족하다고 말한다.

의식(Consciousness)은 크게 Arousal/Wakefulness과 같은 상태(State)와, Awareness와 같은 내용(Content)으로 나뉜다. 전자는 fMRI, M/EEG, ECoG 등의 장비를 활용해 연구해왔다. 후자는 현상학적 의식(Phenomenal Consciousness)과 접근 의식(Access Consciousness)으로 구분된다. 현상학적 의식은 주관적 경험의 질적 성질인 Qualia와 관련이 있으며, 접근 의식은 고차 인지 기능을 가능하게 하는 정보 처리 프로세스를 포함한다.

<div class="centered-container">
  <figure>
    <img src = "/assets/images/posts/2023/Q2/2023-05-14-AIF and Consciousness/consciousness_classification.png" style="width: 80%; height: auto;">
    <figcaption>
      의식의 두 가지 주요 차원: 의식의 수준(Arousal/Wakefulness)과 의식의 내용(Awareness)
    </figcaption>
  </figure>
</div>

1. **State** of Consciousness: Arousal/Wakefulness
   - 주관적 경험이 가능하거나 불가능한 상태.
2. **Content** of Consciousness: Awareness
   1. **Phenomenal** Consciousness:
      - 의식적 경험의 주관적 질.
   2. **Access** Consciousness:
      - 고차 인지를 가능하게 하는 정보 처리 과정.

현상학적 의식은 그 질적인 성질인 Qualia를 물리적 대상으로 환원할 수 있는지 여부에 따라 David Chalmers의 [의식의 어려운 문제(The Hard Problem)](https://en.wikipedia.org/wiki/Hard_problem_of_consciousness)와 같은 논의가 이루어진다. 한편, Giulio Tononi의 [통합정보이론(Integrated Information Theory; IIT)](https://en.wikipedia.org/wiki/Integrated_information_theory)은 거시적 규모의 동역학을 연구해 현상학적 의식을 설명하려 한다. 접근 의식의 경우, 피실험자의 주관적 경험 보고나 특정 인지 기능의 발현을 유도하는 자극을 통해 연구된다.

> "이처럼 의식 연구에는 다양한 패러다임이 혼재되어 있으며, 각 패러다임은 서로 다른 측면의 의식을 다룬다. 이러한 혼란을 능동추론이 해결하고 통합적인 설명을 제공할 수 있을까?"

---

# II. 프로세스 이론을 위한 프레임워크로서의 능동추론

**자유 에너지 원리(Free Energy Principle)**는 "모든 생물학적 에이전트는 생존을 위해 장기적인 surprise를 최소화하려 한다"는 원리다. 이 원리는 공리적이고 자명해 보이지만, 과학적 이론으로는 반증 불가능하다는 한계가 있다. 대신, 규범적 이론(Normative Theory)으로 간주할 수 있다. 규범적 이론은 실증적 이론과 달리, 사실뿐 아니라 가치 판단을 포함한다.

**예측 프로세싱(Predictive Processing)**은 "두뇌가 Bayesian Inference 메커니즘을 활용해 경험에 기반한 추론을 통해 surprise를 최소화한다"는 가설이다. 예측 오차(Prediction Error)는 자유 에너지로 해석될 수 있으며, 두뇌는 계층적 구조를 통해 이러한 오차를 최소화하려 한다. 이를 위해 (1) 지각(Perception)과 (2) 행동(Action)을 통해 예측 오차를 줄인다.

**능동 추론(Active Inference)**은 예측 프로세싱의 관점을 확장해, 현재뿐만 아니라 과거와 미래에 대해서도 이야기한다. 단순히 surprise를 최소화하는 것이 아니라, 그 기댓값(Expectation)을 최소화하려는 것이다. 이는 (1) 실천적 행동(Exploitation)과 (2) 인식론적 행동(Exploration)을 통해 이루어진다. 이러한 과정은 belief의 정확성과 신뢰도를 추정하는 과정으로도 간주될 수 있다.

---

# III. 의식에 대한 능동추론의 설명

예측 코딩(Predictive Coding) 관점에서 의식의 일부 기능을 설명하는 연구는 [Anil Seth(2012)(의식의 현상학적 성질)](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2011.00395/full)이나 [Mateusz Wozniak(2018)(자아)](https://pubmed.ncbi.nlm.nih.gov/30233474/)에서 이미 다루고 있어, 이 글에서는 생략한다.

능동추론의 창시자인 Karl Friston은 의식을 특정 대상(thing)이 아닌, 추론 과정(inferential process)으로 간주한다. 물론 모든 추론 과정이 의식적인 것은 아니다. 오로지 **(1) 시간적으로 두텁고(Temporal Thickness), (2) 반사실적 깊이가 깊은(Counterfactual Depth) 심층 생성 모형의 추론**만이 의식적이라고 주장한다. 그는 의식이 켜지고 꺼지는 이진적 상태가 아니라, 스펙트럼처럼 연속적인(graded; spectral) 현상이라고 본다.

의식의 내용에 관해서는, 각 계층의 단계에서 추론된 결과로 나타나는 최대 사후 확률이라는 가설이 있다. 일부 학자들은 사후 확률 계층의 중간 부분이 의식의 내용을 형성한다고도 제안한다. 아직 이 주제에 대한 논란이 있지만, 의식의 내용이 추론된 상태라는 점에는 많은 학자가 동의한다.

현상학적 성질에 대한 설명에 있어서, 고차 프로세스는 더 추상적이고 오랜 시간 유지되는 반면, 저차원적 raw 데이터는 짧은 시간 동안만 유지된다. 이러한 시간적 차이가 전형적인 감각적 경험, 메타 인지, 주의 집중, 신뢰도 추정 등의 현상을 설명할 수 있을지 기대된다.

---

# IV. 의식의 계산적 프레임워크로서 능동추론

의식 현상을 설명하기 위한 계산 모델을 만드는 데에는 세 가지 주요 어려움이 있다: (1) 의식 연구의 타겟이 여전히 논란의 중심에 있으며, 각 연구 패러다임마다 상이하다. (2) 의식은 오직 1인칭 관점에서만 접근 가능한 주관적 본성을 지닌다. (3) 신경과학적, 행동적 지표와 관련된 연구 결과가 매우 다양하다. 이처럼 의식의 주관적 경험에 대한 통합적 본성 때문에, 아직 능동추론을 활용한 모델이 존재하지 않는다.
> 능동추론이 이러한 문제들을 해결하고 통합적인 이론을 제시할 수 있을까?

완벽한 역학적 모델은 해당 현상을 생성하는 데 필요한 모든 인과적 관계를 특정할 수 있어야 한다. 따라서 실험 데이터를 통해 검증 가능해야 하며, 다양한 수학적/통계적 방법을 적용해 모델의 관련성을 확인할 필요가 있다. 즉, 모델을 검증하기 위해 (1) 실제 실험 데이터와 (2) 방법론적 관행을 적절히 활용해야 한다.

---

# V. 앞으로의 과제

능동추론을 기반으로 한 의식의 계산 모델은 아직 초기 단계에 있다. 이러한 모델들은 실험 데이터를 통해 검증될 필요가 있다. 최근 Maxwell Ramstead는 현상학적 데이터와 생성모형을 연결하려는 **계산 현상학(Computational Neuro-phenomenology)** 시도를 하고 있다.

---

Karl Friston은 2017년 AEON에 "The Mathematics of Mind-Time"이라는 칼럼을 발표한 이후, 의식에 대해 꾸준한 관심을 보여왔다. 그는 Neuropsychoanalyst인 Mark Solms와 함께 position paper를 작성하거나, 자신의 제자인 Maxwell Ramstead와 함께 관련 연구를 지도하고 있다. 의식이라는 개념은 철학적 관점에서도 정의가 다양하기 때문에, 한 가지 프레임워크에서 언어와 개념을 정립하고 담론을 구성하는 이 시도가 학계에서 중요한 사건이 될 수 있을 것으로 생각한다.

이 논문을 통해 Bayesian Brain Hypothesis에서 출발한 Active Inference가 어떻게 의식을 설명하려고 노력하는지 확인할 수 있었다. 구체적인 모델이 아직 제안되지 않았다는 점에서 이 분야는 매우 도전적이다. 앞으로의 논의와 그 결과가 기대된다.

한편, 이러한 논의 이전에 Connectionism이 과연 유의미한지 파악할 필요가 있지 않을까 싶다. 정보적으로 homomorphic한 계산 과정이 실제로 물리적 관점에서 의식이나 지적인 현상을 구현할 수 있을지 의문이다. 여러 질문이 떠오르는 좋은 가이드가 되었다. 참조된 논문들을 깊이 읽어봐야겠다.

### References

[1] [Vilas, M. G., Auksztulewicz, R., & Melloni, L. (2021). Active Inference as a Computational Framework for Consciousness. Review of Philosophy and Psychology, 13(4), 859–878. https://doi.org/10.1007/s13164-021-00579-w](https://psycnet.apa.org/record/2021-75550-001)

[2] [Adapted from Laureys S (2005) The neural correlate of (un)awareness: Lessons from the vegetative state. Trends in Cognitive Sciences 9: 556–559.](https://pubmed.ncbi.nlm.nih.gov/16271507/)
