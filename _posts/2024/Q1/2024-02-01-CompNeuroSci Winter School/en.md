---
title: "Computational Neuroscience Winter School"
scope:
  type: posts
values:
  layout: single
  author_profile: true
  read_time: true
  comments: true
  share: true
  related: true
# toc: false
# toc_sticky: true
# toc_label:
category: Movement
tags: [extracurricular, neuroscience, cognitive science, winter school]
lang: en
header:
  teaser: "/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/13.jpg"
image: assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/13.jpg
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

  /* Newly added styles */
  .two-fig-container {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 20px; /* Space between images */
      flex-wrap: wrap; /* Wrap images vertically on narrower screens */
  }
  .two-fig-container figure {
      width: calc(50% - 20px); /* Set each figure to take up half the width */
      box-sizing: border-box; /* Include padding and borders in the width */
  }

  /* Stack figures vertically on smaller screens */
  @media (max-width: 768px) {
      .two-fig-container figure {
          width: 100%; /* Full width for each figure on small screens */
      }
  }

  /* Three figures layout */
  .three-fig-container {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 20px;
      flex-wrap: wrap;
  }
  .three-fig-container figure {
      width: calc(33% - 20px);
      box-sizing: border-box;
  }

  @media (max-width: 768px) {
      .three-fig-container figure {
          width: 100%;
      }
  }
</style>

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/poster.jpg" style="width: 65%; height: auto;">
      <figcaption>
        Poster for the 2024 Korean Computational Neuroscience Winter School.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/schedule.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Winter school schedule.
      </figcaption>
    </figure>
  </div>
</div>

Recently, I came across news that the Korean Computational Neuroscience Winter School was being held at KAIST, and I immediately decided to look into it. The Korean Society for Computational Neuroscience, founded by my mentor, Professor Seung-Hwan Kim of POSTECH, has long been running this program to spark interest in the brain and neuroscience among young students and the general public. Given the relevance of these lectures to cutting-edge AI development, I was fortunate to receive financial support from my company to attend the winter school.

The winter school spanned four days and was held in the auditorium of the Jeong Mun-Sul Building at KAIST. Renowned Korean neuroscientists and professors gathered to introduce their research to participants from various backgrounds. The theme of this year’s winter school was closely tied to artificial intelligence, with a focus on simulation and modeling-based research, though there were also talks on human and animal experiments.

Through Professor Sang-Hoon Lee's lecture from Seoul National University’s Brain and Cognitive Sciences department, I was introduced to the relationships between neural, computational, and mental activities, along with research plans in these areas. Following this, Professor Jaeseung Jeong provided an in-depth look at the history of computational neuroscience, and Professor Sae-Byul Baek discussed the biological complexity of the brain from an evolutionary perspective. A particularly memorable part of Professor Baek’s lecture was his critique of the “Tabula Rasa” paradigm—a core assumption in AI and machine learning research. The debate of nature versus nurture remains as crucial as ever.

---

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/06.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Professor Sang-Wan Lee discussing brain-inspired AI research.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/07.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Neuroscience-AI Fusion Research Center.
      </figcaption>
    </figure>
  </div>
</div>

On another note, I found Professor Sang-Wan Lee’s lecture on the intersection of AI and neuroscience particularly fascinating. I had previously requested a meeting with him, which he graciously accepted, though I recall feeling somewhat regretful afterward—perhaps due to asking less prepared questions or not having a meaningful exchange. Despite this, Professor Lee’s research direction remains highly aligned with my own interests. I would love to receive his mentorship, though it may be challenging due to the many students already in his lab.

Neuroscience and AI fusion research is concentrated in some of the world’s top research universities. Professor Lee highlighted institutions such as CALTECH, MIT, Oxford, UCL, Columbia University, New York University, TU Berlin, Max Planck Institute for Intelligent Systems, University of Zurich, and KAIST's Center for Neuroscience-Inspired Artificial Intelligence. Completing a master’s program at one of these institutions before pursuing a PhD seems like a solid plan.

---

<div class="centered-container">
  <div class="three-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/02.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Experiment using a cat, recording neural activity responding to specific angles.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/03.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Orientation preferences measured from neural activity.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/04.jpg" style="width: 80%; height: auto;">
      <figcaption>
        Group activity: ordering time-series data from 10 neurons.
      </figcaption>
    </figure>
  </div>
</div>

During the winter school, participants were assigned to teams based on their backgrounds to work on group projects. The challenge presented by Professor Sae-Byul Baek involved analyzing the orientation preferences of neurons in the brain using time-series data. Our team consisted of three members with neuroscience backgrounds, myself with a mathematics background, and the youngest participant, a high school student. A graduate student with a neuroscience background led the team, diving deep into the problem.

Rather than focusing solely on finding the correct answer, we prioritized building a clear and logical argument. I was confident that even the high school student could contribute meaningfully, so we focused on identifying indisputable facts from the data. As a result, we established the following key assumptions:

- (Assertion 1) Each neuron has a unique, **average** response to stimuli.
- (Assertion 2) The unique average response of each neuron exhibits **periodicity**.
- (Assertion 3) The **average firing pattern** of each neuron in response to angular stimuli can be explained by (1) a preferred angle $\theta_0$, (2) sensitivity to the stimulus $I_0$, and (3) an error term $\text{offset}$.
- (Assertion 4) The distribution of time intervals until a neuron fires follows an **exponential distribution** with a unique 𝜆 parameter.

Using these assumptions, we conducted exploratory data analysis and discovered that V1 neurons exhibit unique responses to stimuli. Analysis in polar coordinates revealed a pattern with a periodicity of π in the neurons' average firing rates in response to angular stimuli. Reflecting this characteristic, we assumed that the firing patterns followed a trigonometric function with a period of π for curve fitting in the sample data interval [50-350]s and the test data interval [400-700]s (Assertion 3). The modeling equation is as follows ($i$ represents the cell index):

$$
N^i_{during\ 300s}(t)=I^i_0\cdot \cos(2(\theta-\theta^i_0))+\text{offset}^i
$$

---

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/10.jpg" style="width: 75%; height: auto;">
      <figcaption>
        Our team gathered on the first night to work on the group project.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/09.jpg" style="width: 75%; height: auto;">
      <figcaption>
        Gathering the night before the group project presentation to finalize our report.
      </figcaption>
    </figure>
  </div>
</div>

Our team found the problem highly engaging and spent significant time working on it. On the first night, we introduced ourselves and had an ice-breaking session before diving into the project, revising our plans daily. Before the presentation, we dedicated many hours to preparation, leading to the completion of a Colab-based data analysis guide (**[link](https://colab.research.google.com/drive/1s83DxcG1oilpJp6JVC2kzAjNdkRUXgm7?usp=sharing)**).

---

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/08.jpg" style="width: 80%; height: auto;">
    <figcaption>
      I was chosen to present our group project.
    </figcaption>
  </figure>
</div>

Finally, the last day of the winter school arrived. We steadied our nerves and calmly presented the content we had prepared, concluding our presentation with a sense of pride in the logical and critical approach we had taken.

<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/13.jpg" style="width: 100%; height: auto;">
      <figcaption>
        We were fortunate to win first place in the group activities!
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/12.jpg" style="width: 75%; height: auto;">
      <figcaption>
        A photo taken after receiving our award.
      </figcaption>
    </figure>
  </div>
</div>

To our surprise, the professors were most impressed with our team’s presentation and performance in the group project! We were honored to receive first place in the group activities. Our strategy of ensuring each team member felt fulfilled and created lasting memories seemed to pay off. Achieving good results was a byproduct of consistently working in the right direction. We proudly affirm that even if we hadn’t won first place, the experience would have been invaluable. I’ll end with a letter written to me by Heeyeon Bang, the youngest participant in the winter school and the vibrant spirit of our team:

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q1/2024-02-01-CompNeuroSci Winter School/11.jpg" style="width: 50%; height: auto;">
    <figcaption>
      A letter from Heeyeon Bang, the only high school participant and the “vitamin” of our team.<br>Thank you for all your hard work, Heeyeon!
    </figcaption>
  </figure>
</div>
