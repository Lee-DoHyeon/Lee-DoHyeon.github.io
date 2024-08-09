---
title: An Active Inference Perspective on Consciousness
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
toc_label: "An Active Inference Perspective on Consciousness"
category: Motivation
tags: [Consciousness, Active Inference, Neuroscience, Paper]
lang: en
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

> "Recently, Karl Friston's active inference framework has been increasingly used to explain various brain functions. Could this framework also provide an explanation for consciousness?"

> This post is a reflection on Lucia Melloni et al.'s paper "Active Inference As a Computational Framework for Consciousness."

# I. Theories of Consciousness and the Problem of Explanation

**The Mystery of Consciousness**

In the 1990s, Crick and Koch sought to study consciousness by focusing on Neural Correlates of Consciousness (NCC). NCC refers to the minimal set of neural mechanisms required for a specific conscious experience. However, there is little consensus on the implications or results of NCC research. The authors identify this as the 'Explanandum Problem,' highlighting the lack of a unified explanation for consciousness.

Consciousness can be broadly categorized into state (Arousal/Wakefulness) and content (Awareness). The former has been studied using tools like fMRI, M/EEG, and ECoG. The latter is divided into Phenomenal Consciousness, which relates to the qualitative aspects of subjective experience, and Access Consciousness, which involves the information processing that enables higher cognitive functions.

<div class="centered-container">
  <figure>
    <img src = "/assets/images/posts/2023/Q2/2023-05-14-AIF and Consciousness/consciousness_classification.png" style="width: 80%; height: auto;">
    <figcaption>
      The two major dimensions of consciousness: the level of consciousness (Arousal/Wakefulness) and the content of consciousness (Awareness).
    </figcaption>
  </figure>
</div>

1. **State** of Consciousness: Arousal/Wakefulness
   - A state in which having a subjective experience is possible or not.
2. **Content** of Consciousness: Awareness
   1. **Phenomenal** Consciousness:
      - The subjective qualities of conscious experience.
   2. **Access** Consciousness:
      - Processes that enable specific information for higher-level cognition.

The discussion around phenomenal consciousness often involves whether these qualitative aspects, or Qualia, can be reduced to physical entities—a debate exemplified by David Chalmers' [Hard Problem of Consciousness](https://en.wikipedia.org/wiki/Hard_problem_of_consciousness). Meanwhile, Giulio Tononi's [Integrated Information Theory (IIT)](https://en.wikipedia.org/wiki/Integrated_information_theory) explores the macro-scale dynamics to explain phenomenal consciousness. Access consciousness, on the other hand, is studied through reports of subjective experience or by presenting stimuli that elicit specific cognitive functions in participants.

> "As consciousness research involves various paradigms, each focusing on different aspects, could active inference help resolve these discrepancies and provide a unified explanation?"

---

# II. Active Inference as a Framework for Process Theories

**The Free Energy Principle** states that "all biological agents minimize long-term surprise to adapt to their environment for survival." While this principle is axiomatic and self-evident, it is not falsifiable and therefore cannot be considered a scientific theory in the positivist sense. Instead, it is regarded as a normative theory, which differs from positivist theories by incorporating value judgments rather than dealing solely with empirical facts.

**Predictive Processing** builds on the idea that "the brain minimizes surprise by using Bayesian inference mechanisms to make predictions about the world based on past experiences." Prediction errors, which can be understood as free energy, are minimized by the brain through a hierarchical structure. To reduce prediction errors, the brain can engage in (1) perception to infer about the world or (2) actions to sample the environment.

**Active Inference** extends predictive processing by not only addressing the present but also considering past and future states. Specifically, it seeks to minimize the expected value of surprise rather than just surprise itself. This minimization can be achieved through (1) pragmatic actions (Exploitation) or (2) epistemic actions like exploration (Exploration). This process can be seen as estimating the accuracy and reliability of beliefs.

---

# III. Explaining Consciousness through Active Inference

Explanations of specific functions of consciousness from the predictive coding perspective can be found in studies like [Anil Seth (2012) (Phenomenal Qualities of Consciousness)](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2011.00395/full) or [Mateusz Wozniak (2018) (Self)](https://pubmed.ncbi.nlm.nih.gov/30233474/), so I will not go into detail here.

Karl Friston, the founder of active inference, posits that consciousness is not a "thing" but rather an inferential process. However, not all inferential processes are conscious. Only those inferential processes with **(1) Temporal Thickness and (2) Counterfactual Depth within deep generative models** are considered conscious. Friston argues that consciousness is not a binary state but rather a graded, spectral phenomenon.

Regarding the content of consciousness, one hypothesis suggests that it corresponds to the most probable posterior state at each hierarchical level. Some scholars propose that consciousness content lies within the mid-levels of these posterior hierarchies. While there is still debate, there is general agreement that the content of consciousness is a state of inference.

In terms of phenomenal properties, higher-order processes tend to be more abstract and persist longer, while low-dimensional raw data are retained for shorter periods. This temporal difference might help explain sensory experiences, meta-cognition, attention, and confidence estimation.

---

# IV. Active Inference as a Computational Framework for Consciousness

There are three main challenges in developing computational models to explain consciousness: (1) The target of consciousness research remains contentious, and each paradigm has different focuses. (2) Consciousness has a subjective nature that is only accessible from a first-person perspective. (3) There is a wide range of neuroscientific and behavioral indicators with diverse findings. Because of the integrated nature of subjective experience, no model using active inference currently exists.
> Can active inference address these issues and propose a unified theory of consciousness?

A complete mechanistic model must identify all causal relationships necessary to generate the phenomenon in question. It must also be testable through simulations using experimental data, applying various mathematical/statistical practices to verify the model's relevance. In short, to validate the model, we need to properly utilize (1) empirical data and (2) methodological practices.

---

# V. Future Directions

Computational models aiming to explain the content of consciousness using active inference are still in their infancy. These models must be validated through empirical data. Recently, Maxwell Ramstead has been attempting to connect phenomenological data with generative models in what is termed **Computational Neuro-phenomenology**.

---

Since publishing a column titled "The Mathematics of Mind-Time" in AEON in 2017, Karl Friston has continued to show a keen interest in consciousness. He has co-authored a position paper with Neuropsychoanalyst Mark Solms and is guiding related research with his student Maxwell Ramstead. Given the diverse philosophical definitions of consciousness, this effort to establish language and concepts within a single framework and to construct a coherent discourse could be a monumental event in academia.

Reading this paper, I was able to see how Active Inference, which began with the Bayesian Brain Hypothesis, is attempting to explain consciousness. The absence of a concrete model makes this field particularly challenging, but I am excited to see how these discussions will evolve and how the results will be interpreted.

Before diving into these discussions, however, it might be necessary to assess whether Connectionism is truly meaningful. Can computational processes that are informationally homomorphic actually manifest consciousness or intelligent phenomena from a physical perspective? This paper has sparked many questions, and I plan to explore the referenced studies in greater depth.

### References

[1] [Vilas, M. G., Auksztulewicz, R., & Melloni, L. (2021). Active Inference as a Computational Framework for Consciousness. Review of Philosophy and Psychology, 13(4), 859–878. https://doi.org/10.1007/s13164-021-00579-w](https://psycnet.apa.org/record/2021-75550-001)

[2] [Adapted from Laureys S (2005) The neural correlate of (un)awareness: Lessons from the vegetative state. Trends in Cognitive Sciences 9: 556–559.](https://pubmed.ncbi.nlm.nih.gov/16271507/)
