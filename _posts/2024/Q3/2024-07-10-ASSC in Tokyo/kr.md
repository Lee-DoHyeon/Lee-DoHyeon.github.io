---
title: "의식과학연합학슬회 in Tokyo"
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
toc_label: "의식과학연합학슬회 in Tokyo"
category: Movement
tags: [의식, 과학, 신경과학, 정보과학, 물리학, 철학, 학회, 워크샵, 만남]
lang: kr
header:
  teaser: "/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/AIF.jpeg"
image: assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/AIF.jpeg
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

| 이 글은 Thomas Parr, Giovanni Pezzulo의 교재 “[Active Inference](https://direct.mit.edu/books/oa-monograph/5299/Active-InferenceThe-Free-Energy-Principle-in-Mind)”의 마지막 장을 읽고 정리한 글임을 밝힙니다.

<br>

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/AIF_original.jpeg" style="width: 80%; height: auto;">
    <figcaption>
      토마스 파, 지오바니 페줄로, 칼 프리스턴의 능동 추론 교과서
    </figcaption>
  </figure>
</div>

---

# 1. 인트로

능동 추론(Active Inference)은 기존에 심리학과 신경과학 분야에서 독립적으로 존재하던 지각(Perception), 행동 선택(Action Selection), 주의집중(Attention), 감정 조절(Emotion Regulation) 등을 통합적으로 바라보는 새로운 관점을 제공한다. 더 나아가, 기존의 사이버네틱스(Cybernetics), 행동의 관념운동 이론(Ideomotor Theory of Action), 강화 학습(Reinforcement Learning), 최적 제어(Optimal Control)와도 긴밀히 연결된다. 능동 추론은 생물학적, 사회적, 기술적 주제로도 확장될 수 있다.

## 아랫길(Low Road)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/0.gif" style="width: 80%; height: auto;">
    <figcaption>
        뱀의 공격을 예측하고 빠르게 대응하는 고양이, 출처: <a href="forgifs.com/gallery/v/Animals/Cat-vs-snake.gif.html">forgif</a>
      </figcaption>
  </figure>
</div>

모든 감응력 있는(Sentient) 생명체는 환경과 행동-지각의 루프를 이루며 영속(persist)해 나간다. 능동 추론을 이해하는 한 방법은 두뇌를 세상에 대한 생성 모형(Generative Model)을 지닌 예측 기계(Prediction Machine)로 간주하는 것이다. 이는 헬름홀츠(Hermann von Helmholtz)의 아이디어로부터 시작하여 최근에는 베이지안 두뇌 가설(Bayesian Brain Hypothesis)로 발전되었다. 이 관점에 따르면, 정확한 추론은 불가능하기 때문에 근사(Approximation)를 수행하게 되며, 결과적으로 지각과 행동은 변분 자유 에너지(Variational Free Energy)를 최소화하는 과정으로 해석된다. 다시 말해, 행동과 지각은 독립된 개념이라기보다 한 목적을 달성하는 과정의 두 가지 모습으로 볼 수 있다. 미래의 사건에 대한 계획(Planning) 또한 기대 자유 에너지(Expected Free Energy)를 최소화하는 과정으로 해석될 수 있다.

## 윗길(High Road)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/1.png" style="width: 60%; height: auto;">
    <figcaption>
        자유에너지에 대한 곡면 위에서 안정점(Stable Point)를 향해 이동하는 모습, 출처: <a href="https://www.researchgate.net/publication/357198851_Permutation_Entropy_as_a_Universal_Disorder_Criterion_How_Disorders_at_Different_Scale_Levels_Are_Manifestations_of_the_Same_Underlying_Principle">Permutation Entropy as a Universal Disorder Criterion: How Disorders at Different Scale Levels Are Manifestations of the Same Underlying Principle, Rutger Goekoop et al.</a>.<br>점의 상태가 시스템의 궤적을 이룬다.
      </figcaption>
  </figure>
</div>

능동 추론을 이해하는 또 다른 방법은, 생물학적 유기체가 신체를 유지하고 소멸을 막는 핵심 원리에서 시작한다. 마코프 블랭킷(Markov Blanket)은 통계학에서 흔히 사용하는 개념으로, 생명체의 내부와 외부를 구분하는 형식적 프레임워크이다. 마코프 블랭킷을 지닌 유기체는 외부 환경을 베이지안 관점으로 모형화한다고 볼 수 있다. 자율성은 유기체가 지닌 외부 환경의 모형이 존재론적 전제 조건들을 규정하면서도 편향되지 않기 때문에 보장된다. 이로써 지각과 행동을 통해 베이지안 모형 에비던스(Model Evidence)를 최대화하는 과정으로 최적 행동을 서술할 수 있다. 이는 변분 자유 에너지를 최소화하는 과정과 동일하며, 해밀턴의 최소 작용의 원리와 통계 역학의 원리들과도 일맥상통한다.

## 형식화(Formalization)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/2.jpg" style="width: 60%; height: auto;">
    <figcaption>
        능동 추론 및 베이즈 역학, 출처: <a href="https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2018.00021/full">The Active Inference Approach to Ecological Perception: General Information Dynamics for Natural and Artificial Embodied Cognition, Adam Linson et al.</a>.
      </figcaption>
  </figure>
</div>

형식적 관점에서 자유 에너지는 변분 추론(Variational Inference)을 통해 가능하다. 모형이 나타내는 과정(Process)은 변수와 시간의 이산성/연속성에 상관없이 모형화될 수 있다.

## 과정 이론(Process Theory)

능동 추론은 단순히 규범적 원리(Normative Theory)에서 그치는 것이 아니라, 실제로 이것들이 뇌에서 어떻게 구현되어 있는지 분석하는 과정 이론(Process Theory) 또한 제공한다. 해부학적 수준에서 시스템적 수준에 이르기까지, 뉴런들의 신경해부학적 회로(Neuroanatomical Circuitry)와 신경 조절(Neuromodulation)을 포함한 메시지 전달 과정(Neuronal Message Passing)을 설명한다.

## 모델 설계 방법론(Design Recipe)

모든 생명체는 변분 자유 에너지를 최소화하면서도 서로 다르게 행동한다. 이는 그들이 다른 생성 모형을 지녔기 때문이다. 가능한 생성 모형의 레퍼토리는 매우 풍부하며, 시대적 맥락(Context)과 생태적 지위(Niche)에 따라 다른 생물학적 구현체를 지니고 있을 것이다. 진화(Evolution)는 박테리아에서 영장류까지 풍부한 생태적 지위에 맞는 두뇌와 신체의 복잡한 형태를 발견해왔다. 모형을 설계할 때 이 과정을 역설계할 수 있으며, 관심 생물의 두뇌와 신체에 따라 이산/연속 변수를 취하거나 모형의 깊이를 설계할 수 있다.

## 예시(Example)

능동 추론을 통해 지각적 추론, 목표 지향적 행동, 모형의 학습, 행동 선택 등을 모형화할 수 있다.

## 실험(Experiment)

능동 추론은 실험을 통해 수집한 데이터에 대해 모형 기반의 데이터 분석에 사용될 수 있으며, 개인의 생성 모형에 따라 파라미터를 역추적할 수도 있다. 이러한 계산적 형질화(Computational Phenotyping)는 타인의 주관적 모형에 대한 객관적 모형을 설계하고 평가하는 데 도움을 줄 수 있다.

<br>

# 2. 점 연결하기

---

## 데닛의 비판(Dennett’s Critique)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/3.webp" style="width: 50%; height: auto;">
    <figcaption>
        2004년 경의 데니얼 데닛, 출처: <a href="https://static01.nyt.com/images/2024/04/19/multimedia/19Dennett-2-mvpq/19Dennett-2-mvpq-superJumbo.jpg?quality=75&auto=webp">Eamonn McCabe/Popperfoto, via Getty Images</a>.
      </figcaption>
  </figure>
</div>

수십 년 전, 철학자 대니얼 데닛(Daniel Dennett)은 인지 과학자들이 명확히 구분하기 어려운 독립된 하위 시스템(subsystem)을 모형화하는 데에 너무 많은 시간을 쓴다고 불평한 적 있다. 그는 오히려 다루고자 하는 환경적 지위를 잘 설정하여 전체적인 인지적 생명체(cognitive creature)를 모형화해야 한다고 제안했다.

## 통합적 관점(Integrative Perspective)

능동 추론(Active Inference)은 통합적인 관점을 제공한다. 지각과 행동은 생성 모형(generative model)에 대해 자증적(self-evidencing)이며, 변분 자유 에너지를 최소화하는 과정의 서로 다른 측면이다. 장기 기억(long-term memory)은 생성 모형의 매개변수를 학습하는 과정에서 발달하며, 작업 기억(working memory)은 과거와 미래의 외부 상태에 대한 믿음을 갱신(belief updating)하는 과정이다. 이때 주의 집중(attention)은 감각 입력의 신뢰도(precision)에 대한 믿음을 최적화(belief optimization)하는 과정이다. 계획(planning)과 지향성(intentionality)의 형태 또한 가능한 미래의 시나리오 중 하나를 선택하는 능력으로 개념화될 수 있으며, 이는 시간적으로 깊은 생성 모형(deep temporal model)을 요구한다. 시간적으로 깊은 생성 모형은 현재에 대한 믿음을 바탕으로 과거에 대한 믿음을 갱신하는 회상(retrospection)과 현재의 믿음을 바탕으로 미래에 대한 믿음을 도출하는 전망(prospection)이라는 복잡한 현상을 이해하는 데에도 도움을 준다. 마지막으로, 내수용적 조절(interoceptive regulation)과 감정(emotion) 또한 미래 사건의 이상성(allostatic) 결과를 예측하는 내부 생리 메커니즘의 생성 모형을 통해 개념화될 수 있다.

## 비전(Vision)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/4.jpg" style="width: 50%; height: auto;">
    <figcaption>
        1880년 경의 윌리엄 제임스, 출처: <a href="https://www.loa.org/writers/29-william-james/">Houghton Library at Harvard University; public domain via Wikimedia Commons</a>.
      </figcaption>
  </figure>
</div>

데닛의 비판에 맞서, 능동 추론은 수많은 독립적으로 다뤄져 온 인지 및 행동 개념들에 대한 통합적인 관점을 제공한다. 이에 따라, 단순히 지각과 행동, 기억과 주의 집중들을 조합하는 것이 아니라, 생명체가 해결해야만 하는 최초 원리로부터 그들이 이끌어낸 다양한 인지 기능들을 분석하게 해준다. 이로써, 심리학과 신경과학에서 사용되어 온 윌리엄 제임스의 범주(Jamesian category)가 지닌 모호성을 벗어나 수학적 형식성과 구체성을 지닐 수 있게 된다.

## 유사성(Identifying Analogies)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/5.png" style="width: 70%; height: auto;">
    <figcaption>
        의사결정에 있어 항상 등장하는 탐색-실행 딜레마(Exploration-Exploitation Dillema), 출처: <a href="https://www.lakera.ai/blog/reinforcement-learning">Lakera AI</a>.
      </figcaption>
  </figure>
</div>

이러한 규범적 관점을 채택하는 것은 다른 분야에서 연구된 인지 현상 사이의 형식적인 유사성을 쉽게 식별하는 데 도움을 준다. 대표적으로 탐색과 활용의 딜레마(exploration-exploitation dilemma)나 제한된 자원에서의 검색과 숙고의 딜레마(search-deliberation dilemma)에 대한 연결성을 쉽게 이해하도록 도와준다

## 오해풀기(Demystifying)

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/6.webp" style="width: 50%; height: auto;">
    <figcaption>
        하트 모양 번개, 출처: <a href="https://www.reddit.com/r/interestingasfuck/comments/9pjauj/a_heart_shaped_lightning_bolt_during_a/?rdt=40244&onetap_auto=true&one_tap=true">Reddit</a>.
      </figcaption>
  </figure>
</div>

결론적으로, 능동 추론은 과정 이론(process theory)으로서 뉴런이 수행하는 계산을 이해하는 핵심 수단을 제공한다. 두뇌-마음-행동은 단순히 변분 자유 에너지를 최소화하는 과정으로 이해될 수 있다. 다시 말해, 천둥과 번개가 대기의 방전 현상에 대한 청각적, 시각적 일면이듯이, 두뇌-마음-행동은 변분 자유 에너지를 최소화하는 과정의 다양한 일면일 뿐이다. 현대 과학이 천둥을 번개로, 번개를 천둥으로 환원시키지 않고 대기의 방전 현상으로 환원시켜 이해하듯이, 두뇌, 마음, 행동의 관계가 지니는 미스터리를 떠나 자유 에너지의 최소화 현상으로 환원시켜 이해하는 것이 바람직하다.

# Summary

> 이 책은 뇌와 행동을 첫 원칙에서 이해하는 가능성에 대한 질문으로 시작하여, 능동 추론을 그 해결책으로 제시했다. 능동 추론이 인식, 행동 선택, 감정 등 익숙한 심리학적 개념에 어떤 의미를 가지는지 탐구하면서, 관련 개념들을 재검토하고 앞으로의 연구 과제를 제시했다. 이론적 신경생물학의 중요한 실습을 통해 능동 추론을 실천해 볼 것을 권장하며, 일상 생활에서도 이를 적용할 수 있음을 강조했다. 궁극적으로, 능동 추론이 우리의 일상과 연구에 어떻게 기여할 수 있는지를 강조하며, 독자들이 이를 계속 추구할 것을 기대한다.
