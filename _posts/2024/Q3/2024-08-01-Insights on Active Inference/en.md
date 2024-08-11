---
title: "Insights on Active Inference"
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
toc_label: "Insights on Active Inference"
category: Motivation
tags:
  [
    Theory,
    Neuroscience,
    Mind,
    Behavior,
    Brain,
    Philosophy,
    Science,
    Engineering,
  ]
lang: en
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

| This post is based on the final chapter of the textbook “[Active Inference](https://direct.mit.edu/books/oa-monograph/5299/Active-InferenceThe-Free-Energy-Principle-in-Mind)” by Thomas Parr and Giovanni Pezzulo.

<br>

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/AIF_original.jpeg" style="width: 80%; height: auto;">
    <figcaption>
      The Active Inference textbook by Thomas Parr, Giovanni Pezzulo, and Karl Friston
    </figcaption>
  </figure>
</div>

---

# 1. Introduction

Active Inference offers a new perspective that integrates previously separate concepts in psychology and neuroscience, such as perception, action selection, attention, and emotion regulation. Furthermore, it connects closely with existing frameworks like cybernetics, the ideomotor theory of action, reinforcement learning, and optimal control. Active Inference can also extend to biological, social, and technological domains.

## The Low Road

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/0.gif" style="width: 80%; height: auto;">
    <figcaption>
        A cat quickly reacting to a snake’s attack, anticipating the threat. Source: <a href="forgifs.com/gallery/v/Animals/Cat-vs-snake.gif.html">forgif</a>
      </figcaption>
  </figure>
</div>

All sentient beings exist within a loop of action and perception with their environment. One way to understand Active Inference is by considering the brain as a prediction machine equipped with a generative model of the world. This idea, originating from Hermann von Helmholtz, has evolved into the Bayesian Brain Hypothesis. According to this view, exact inference is impossible, leading to approximations where perception and action minimize variational free energy. In other words, action and perception are not independent concepts but two sides of the same process aimed at achieving a goal. Planning for future events can also be seen as a process of minimizing expected free energy.

## The High Road

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/1.png" style="width: 60%; height: auto;">
    <figcaption>
        Moving toward a stable point on a free energy surface. Source: <a href="https://www.researchgate.net/publication/357198851_Permutation_Entropy_as_a_Universal_Disorder_Criterion_How_Disorders_at_Different_Scale_Levels_Are_Manifestations_of_the_Same_Underlying_Principle">Permutation Entropy as a Universal Disorder Criterion: How Disorders at Different Scale Levels Are Manifestations of the Same Underlying Principle, Rutger Goekoop et al.</a>
      </figcaption>
  </figure>
</div>

Another way to understand Active Inference starts with the core principle that biological organisms maintain their bodies and prevent their demise. The Markov blanket, a concept commonly used in statistics, provides a formal framework that distinguishes between an organism's internal and external states. An organism with a Markov blanket can model the external environment from a Bayesian perspective. Autonomy is ensured because the organism’s model of the external environment sets ontological preconditions without bias. Optimal behavior can be described as a process of maximizing Bayesian model evidence through perception and action. This process is equivalent to minimizing variational free energy and aligns with Hamilton’s principle of least action and principles from statistical mechanics.

## Formalization

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/2.jpg" style="width: 60%; height: auto;">
    <figcaption>
        Active Inference and Bayesian Mechanics. Source: <a href="https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2018.00021/full">The Active Inference Approach to Ecological Perception: General Information Dynamics for Natural and Artificial Embodied Cognition, Adam Linson et al.</a>
      </figcaption>
  </figure>
</div>

From a formal perspective, free energy is minimized through variational inference. The processes represented by a model can be modeled regardless of whether variables and time are discrete or continuous.

## Process Theory

Active Inference is not just a normative principle but also provides a process theory that analyzes how these principles are implemented in the brain. It explains neural message passing, including the neuroanatomical circuitry and neuromodulation, from the anatomical level to the systemic level.

## Design Recipe

All organisms minimize variational free energy but do so differently because they have different generative models. The repertoire of possible generative models is rich and depends on the context and ecological niche, resulting in different biological implementations. Evolution has discovered complex forms of brains and bodies suited to diverse ecological niches, from bacteria to primates. When designing models, this process can be reverse-engineered, allowing for the design of models with discrete or continuous variables and varying depths depending on the brains and bodies of interest.

## Example

Active Inference can be used to model perceptual inference, goal-directed behavior, model learning, action selection, and more.

## Experimentation

Active Inference can be used for model-based data analysis on data collected from experiments, allowing for parameter back-calculation based on individual generative models. This computational phenotyping helps design and evaluate objective models of subjective models of others.

<br>

# 2. Connecting the Dots

---

## Dennett’s Critique

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/3.webp" style="width: 50%; height: auto;">
    <figcaption>
        Daniel Dennett around 2004. Source: <a href="https://static01.nyt.com/images/2024/04/19/multimedia/19Dennett-2-mvpq/19Dennett-2-mvpq-superJumbo.jpg?quality=75&auto=webp">Eamonn McCabe/Popperfoto, via Getty Images</a>
      </figcaption>
  </figure>
</div>

Decades ago, philosopher Daniel Dennett complained that cognitive scientists spent too much time modeling independent subsystems that are difficult to distinguish clearly. He suggested that they should instead focus on modeling the entire cognitive creature by properly setting the environmental niche they are dealing with.

## Integrative Perspective

Active Inference provides an integrative perspective. Perception and action are self-evidencing with respect to a generative model, representing different aspects of the process of minimizing variational free energy. Long-term memory develops as the generative model learns its parameters, while working memory is the process of belief updating about past and future external states. During this time, attention optimizes belief about the precision of sensory input. Planning and intentionality can be conceptualized as the ability to select among possible future scenarios, requiring a deep temporal generative model. This deep temporal model also helps understand complex phenomena like retrospection, where beliefs about the past are updated based on current beliefs, and prospection, where beliefs about the future are derived from current beliefs. Finally, interoceptive regulation and emotion can also be conceptualized through generative models of internal physiological mechanisms predicting allostatic outcomes of future events.

## Vision

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/4.jpg" style="width: 50%; height: auto;">
    <figcaption>
        William James around 1880. Source: <a href="https://www.loa.org/writers/29-william-james/">Houghton Library at Harvard University; public domain via Wikimedia Commons</a>
      </figcaption>
  </figure>
</div>

In response to Dennett’s critique, Active Inference offers an integrative view of many cognitive and behavioral concepts that have been studied independently. It allows us to analyze the various cognitive functions derived from the first principles that life must solve, rather than merely combining perception, action, memory, and attention. This approach gives mathematical formality and specificity, moving beyond the ambiguity of William James' categories that have been used in psychology and neuroscience.

## Identifying Analogies

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/5.png" style="width: 70%; height: auto;">
    <figcaption>
        The exploration-exploitation dilemma always present in decision-making. Source: <a href="https://www.lakera.ai/blog/reinforcement-learning">Lakera AI</a>
      </figcaption>
  </figure>
</div>

Adopting this normative perspective makes it easier to identify formal analogies between cognitive phenomena studied in different fields. Notably, it helps understand the connections between the exploration-exploitation dilemma and the search-deliberation dilemma in constrained resources.

## Demystifying

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-01-Insights on Active Inference/6.webp" style="width: 50%; height: auto;">
    <figcaption>
        Heart-shaped lightning bolt. Source: <a href="https://www.reddit.com/r/interestingasfuck/comments/9pjauj/a_heart_shaped_lightning_bolt_during_a/?rdt=40244&onetap_auto=true&one_tap=true">Reddit</a>
      </figcaption>
  </figure>
</div>

In conclusion, Active Inference, as a process theory, offers a key means of understanding the computations performed by neurons. Mind-brain-behavior can be understood simply as a process of minimizing variational free energy. In other words, just as thunder and lightning are auditory and visual aspects of atmospheric discharge, mind-brain-behavior are different aspects of the process of minimizing variational free energy. Just as modern science understands thunder and lightning not by reducing them to each other but by reducing both to atmospheric discharge, the mysteries of the relationship between brain, mind, and behavior are best understood by reducing them to the process of minimizing free energy.

# Summary

> This book began with the question of understanding the brain and behavior from first principles, proposing Active Inference as the solution. It explored what Active Inference means for familiar psychological concepts like perception, action selection, and emotion, while reexamining related concepts and proposing future research directions. Through practical exercises in theoretical neurobiology, it encouraged practicing Active Inference, emphasizing its applicability to everyday life. Ultimately, the book highlighted how Active Inference can contribute to both our daily lives and research, encouraging readers to continue pursuing this approach.
