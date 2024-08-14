---
title: 아마리 슌이치, "뇌, 마음, 인공지능"
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
toc_label: "아마리 슌이치: 뇌, 마음, 인공지능"
category: Motivation
tags: [두뇌, 계산장치, 신경과학, 정보이론, 인공지능]
lang: kr
header:
   teaser: "/image: assets/images/posts/2023/Q3/2023-09-23-Brain, Mind, and AI/main.jpg"
image: assets/images/posts/2023/Q3/2023-09-23-Brain, Mind, and AI/main.jpg
---

<style>
   .container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
   }

   .image-wrapper {
      width: 48%;
      margin: 1%;
      box-sizing: border-box;
      text-align: center;
   }

   .image-wrapper img {
      width: 100%;
      height: auto;
      display: block;
   }

   .image-wrapper figcaption {
      font-family: Arial, sans-serif;
      font-size: 14px;
      color: #555;
      margin-top: 8px;
   }

   @media (max-width: 768px) {
      .image-wrapper {
            width: 100%;
      }
   }
</style>

> [뇌, 마음, 인공지능](https://product.kyobobook.co.kr/detail/S000001732224)

| 저자: [아마리 슌이치](https://en.wikipedia.org/wiki/Shun%27ichi_Amari)

아마리 슌이치의 "뇌, 마음, 인공지능"을 읽고 기억에 남는 부분을 정리한 내용이다. 아마리 슌이치는 이 책에서 딥러닝 발전의 초기, 자신의 업적에 대해 많이 알려지지 않은 점에 대해 아쉬움을 표현하고 있다. 도쿄대학교의 수리공학과 출신의 그는, 아주 오래 전부터 통계역학과 정보 기하학 등의 첨단 이론을 활용해 인공지능을 연구해 왔다. 그에 대한 공로로 일본 최고의 연구 기관 RIKEN의 수석 연구원으로 재직해왔다. 이 책은 뇌의 구조와 기능, 그리고 인공지능의 발전에 대해 깊이 있는 통찰을 제공한다.

<body>
    <div class="container">
        <figure class="image-wrapper">
            <img src="/assets/images/posts/2023/Q3/2023-09-23-Brain, Mind, and AI/author.jpg" style="width: 80%; height: auto;">
            <figcaption>저자인 아마리 슌이치</figcaption>
        </figure>
        <figure class="image-wrapper">
            <img src="/assets/images/posts/2023/Q3/2023-09-23-Brain, Mind, and AI/main.jpg" style="width: 80%; height: auto;">
            <figcaption>본 책: 뇌, 마음, 인공지능</figcaption>
        </figure>
    </div>
</body>

---

## 2장. 뇌란 무엇인가

이 장에서는 뇌의 신경생리학적 구조와 세부 기능을 설명한다. 뇌는 약 1000억 개의 뉴런으로 이루어진 거대한 회로망으로, 무게는 약 1.4kg, 부피는 1400cc 정도이다. 

### 1. 뇌간

뇌간은 생명 유지의 기본적인 장치로, 호흡과 같은 자율신경 기능을 제어한다. 또한, 수면과 각성을 조절하며 외부에서 대뇌로 들어오는 정보와 대뇌에서 외부로 나가는 정보의 경로가 된다.

### 2. 소뇌

소뇌는 뇌의 10% 정도에 불과한 무게를 차지하지만, 약 800억 개의 뉴런을 가지고 있어 뇌에서 뉴런이 가장 많은 부위다. 주로 지각과 운동 제어를 담당하며, 대뇌와 협력해 정교한 움직임을 조절한다. 대뇌에서 오랜 시간 학습된 운동 기능은 소뇌로 이동해 루틴화되며, 이를 통해 더욱 빠르고 효율적으로 처리된다.

### 3. 대뇌

대뇌는 뇌에서 가장 늦게 발달한 부위다. 대뇌피질, 대뇌기저핵, 해마, 편도체로 구성되어 있으며, 약 200억 개의 뉴런으로 이루어져 있다. 인지, 사고, 언어, 운동 계획과 제어, 기억 등 고차원적인 정신 기능을 담당하며, 이 모든 것이 대뇌에서 이루어진다. 대뇌피질은 약 2000~2500cm²의 표면적을 가지며, 두께는 2~3mm로 매우 얇다. 이 얇은 층은 6개의 층으로 구성되어 있으며, 각각이 기둥 형태의 컬럼을 이루고 있다.

> IT-MPC에서 Optimal Input이 대뇌-소뇌의 운동 기능 상호작용과 어떤 연관이 있을까?

---

## 5장. 수학으로 뇌를 해석한다

이 장에서는 뇌의 학습 메커니즘에 대해 다룬다. 뇌의 신경 회로를 조사해 보면, 학습을 위해 오차가 회로의 역방향으로 흘러가는 '오차 역전파' 현상은 관찰되지 않는다. 그렇다면 퍼셉트론의 학습이 뇌의 구조와 전혀 다른 것일까?

완전히 그렇다고 말하기는 어렵다. 확률강하학습법은 학습 정보 처리의 원리를 알고리즘으로 표현한 것이다. 뇌는 이 원리를 실체화하지 못했을 수도 있다. 따라서 퍼셉트론 학습이 뇌의 구조와 완전히 동떨어진 것이라고 할 수는 없다.

---

## 6장. 인공지능의 역사와 미래

IBM은 뉴로 계산에 본격적으로 참여하기 시작했으며, 미국 국방성의 DARPA가 주도한 "SyNAPSE" 프로그램을 통해 신경 회로를 칩으로 만드는 프로젝트를 추진했다. 이를 바탕으로 IBM은 "TrueNorth"라는 뉴로칩을 개발하는 데 성공했다.

이 뉴로칩은 100만 개의 뉴런과 2억 5600만 개의 시냅스를 포함하고 있으며, 소비 전력은 겨우 70mW에 불과하다. 이 칩을 여러 개 연결하면 4800만 개의 뉴런과 120억 개의 시냅스로 구성된 시스템이 완성되는데, 이는 생쥐의 뇌에 필적한다고 한다.

---

## 읽고 나서

책 "인간 vs 인공지능"에서도 다루었듯이, 현대의 계산 장치는 인간의 정신 현상과는 본질적으로 다른 면이 있다. 그 중에서도 가장 큰 차이는 물리적 특성일 것이다. 어떻게 그렇게 작은 부피와 면적으로 컴퓨터가 풀지 못하는 생존 문제를 해결하고, 생활 경험을 이어나가는지 궁금해진다. 이 복잡성과 에너지 효율성은 과학과 공학적으로 어떻게 접근할 수 있을까? 인공지능의 미래는 하드웨어에 달려 있을지도 모른다. 두뇌에서 일어나는 한 가지 현상의 모방만으로도 현대 공학과 사회를 크게 변화시킨 것처럼, 과학의 힘과 상상력의 파급 효과는 경험해보기 전까지는 아무도 알 수 없다는 생각이 든다.
