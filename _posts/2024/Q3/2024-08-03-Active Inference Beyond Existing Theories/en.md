---
title: "Active Inference: A New Perspective Beyond Existing Theories"
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
toc_label: "Active Inference: A New Perspective Beyond Existing Theories"
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
  teaser: "/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/0.webp"
image: assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/0.webp
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

| This post is a summary of the final chapter of the textbook “[Active Inference](https://direct.mit.edu/books/oa-monograph/5299/Active-InferenceThe-Free-Energy-Principle-in-Mind)” by Thomas Parr and Giovanni Pezzulo.

<br>

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/0.webp" style="width: 50%; height: auto;">
    <figcaption>
      A futuristic robot autonomously exploring its environment, learning, and adjusting its behavior.
    </figcaption>
  </figure>
</div>

# Active Inference vs. Existing Theories

---

### (1) Philosophy; Predictive Theories

Traditional brain and cognitive theories have emphasized feedforward models where stimuli are transformed into responses (with everything in between labeled "cognitive"). However, Active Inference emphasizes prediction and goal-directed aspects. An active inference agent generates predictions based on a generative model, tests hypotheses, updates the model, and actively collects data. This process satisfies both epistemic (information-seeking) and pragmatic (reward-seeking) demands.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/1.gif" style="width: 80%; height: auto;">
    <figcaption>
      A scene from the movie "Dune" where the Kwisatz Haderach foresees the future.
    </figcaption>
  </figure>
</div>

**Predictive Processing** Predictive Processing (PP) is a philosophical framework that views the brain and cognition as prediction-centric, using the concepts of "predictive brain" or "predictive mind." While closely related to Active Inference, PP uses broader concepts such as generative models, predictive coding, free energy, precision modulation, and the Markov blanket. PP has potential applications across various cognitive domains, from perception and behavior to learning and psychopathology, and can integrate simple biological organisms with complex social and cultural structures. Although PP uses familiar concepts like belief and surprise, these terms can have technical meanings. The growing interest in PP has led to diverse theoretical and epistemological interpretations among philosophers, including enactivism, embodied cognition, and non-representational approaches.

### (2) Perception

Active Inference views perception as a process of inference based on a generative model. Bayes' Rule calculates beliefs about hidden states of the environment based on observed data—a concept dating back to Helmholtz (1866) and reinterpreted across psychology, computational neuroscience, and machine learning.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/2.png" style="width: 50%; height: auto;">
    <figcaption>
      The Bayesian Brain Hypothesis: perceiving the world through Bayes' Rule. Source: <a href="">Entropy, Free Energy, Symmetry and Dynamics in the Brain, Viktor Jirsa et al.</a>
    </figcaption>
  </figure>
</div>

**Bayesian Brain Hypothesis** The Bayesian Brain Hypothesis modernizes this idea, applying it to decision-making, sensory processing, learning, and more. Active Inference provides a normative basis for these inference ideas, grounded in the principle of minimizing variational free energy. In contrast, the Bayesian Brain Hypothesis models perception and action differently. Active Inference extends the typical process model of predictive coding in perception to the domain of action, explaining action dynamics through generative model principles. The Bayesian Brain Hypothesis includes various theories across computational, algorithmic, and neuronal levels, each with competing theories and multiple ways of implementing Bayesian computation. Active Inference, on the other hand, offers a more integrated perspective by connecting normative principles with process theories. All processes are assumed to minimize free energy, and process theories use gradient descent on free energy, with clear neurophysiological implications. Predictive coding can be derived from the free energy minimization principle and extended to the action domain by adding motor reflexes to the predictive coding agent in continuous time.

### (3) Action Control

In Active Inference, action control is driven by forward prediction, similar to perceptual processing. For instance, the proprioceptive prediction "My hand will grasp the cup" triggers the grasping movement. Action control, unlike perception, relies less on sensory input and is more connected to motor reflexes in the brainstem and spinal cord, receiving relatively less bottom-up input. This is related to the equilibrium point hypothesis, where action sets and maintains a target equilibrium point. To initiate action, prior beliefs and sensory precision must be appropriately modulated; when the prior is more precise, the grasping action occurs. This is achieved through transient sensory attenuation, and failure in sensory attenuation can lead to failure in action control.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/3.jpg" style="width: 60%; height: auto;">
    <figcaption>
      The ideomotor effect: an example of how prior beliefs alone can influence behavior, as seen with the Ouija board.
    </figcaption>
  </figure>
</div>

**Ideomotor Theory** In Active Inference, actions are driven by proprioceptive predictions rather than motor commands. This concept is related to William James' Ideomotor Theory, which suggests that the bidirectional linkage between actions and effects is central to cognitive architecture. In other words, actions generate sensory predictions when moving from action to effect, and actions can be selected based on the expected effect when moving from effect to action. Active Inference extends these ideas by adding concepts such as precision control and sensory attenuation.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/4.webp" style="width: 60%; height: auto;">
    <figcaption>
      Diagram illustrating the history of cybernetics and related fields. Source: <a href="https://www.researchgate.net/profile/Dmitry-Novikov-4v">Dmitry A. Novikov.</a>
    </figcaption>
  </figure>
</div>

**Cybernetics** Active Inference emphasizes goal-directed behavior and feedback-based agent-environment interaction, similar to the TOTE model (Test-Operate-Test-Exit), selecting actions based on the difference between a preferred state and the current state. This distinguishes it from behaviorist theories or reinforcement learning, which assume a simple stimulus-response relationship. Instead, Active Inference aligns more closely with Perceptual Control Theory, which also emphasizes controlling perceptual states rather than actions. For example, while driving, we control the desired speed but may choose to accelerate or decelerate based on circumstances. This reflects William James' insight that "humans achieve stable goals in a flexible manner." However, while Active Inference includes predictive (feedforward) control through generative models, Perceptual Control Theory assumes that feedback mechanisms alone are sufficient. Both theories describe control through a hierarchical cascade of higher and lower goals, but Active Inference includes a function that prioritizes more salient or urgent goals based on precision-weight modulation by motivational processes.

<div class="centered-container">
  <figure>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/1AR2-OHCxsQ?si=rJ886vqqvCW80lss" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    <figcaption>
      The famous Model Predictive Path Integral; Information-Theoretic Model Predictive Control algorithm used to power a rally car. Source: Georgia Tech.
    </figcaption>
  </figure>
</div>

**Optimal Control Theory** Optimal Control Theory selects motor commands through control policies and cost functions based on stimulus-driven responses. In contrast, Active Inference uses predictive control, where motor commands are considered predictions, with the generative model playing a central role in action control. While Optimal Control requires both a forward model to predict the outcomes of actions and an inverse model to optimize motor commands based on those predictions, Active Inference relies solely on a simple forward model based on reflexes. When sensory prediction errors arise, Active Inference resolves them through action, using simple motor reflexes rather than complex inverse computations. Additionally, Active Inference replaces the cost/value functions used in Optimal Control Theory with Bayesian concepts such as prior preferences or expected free energy.

### (4) Utility and Decision-Making

Active Inference, Optimal Control Theory, economic theory, and reinforcement learning all utilize costs and rewards in selecting actions, but their approaches differ. Optimal Control Theory and reinforcement learning use cost functions and the Bellman equation to optimize behavior, while economic theory focuses on utility maximization. In contrast, Active Inference aims to minimize expected free energy, naturally resolving the exploration-exploitation dilemma. It absorbs the concept of cost into prior preferences, specifying the goal of control and biasing the generative model, using priors instead of value functions to find the optimal policy. This allows Active Inference to perform actions through predictive control, effectively achieving desired states.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/5.png" style="width: 40%; height: auto;">
    <figcaption>
      Example of Bayesian Decision Theory: Bayesian Search Theory applied to find the wreckage of Flight AF447 using Bayes' Theorem. Source: <a href="https://www.metsci.com/what-we-do/featured-projects/the-search-for-air-france-447/">Metron Inc.</a>
    </figcaption>
  </figure>
</div>

**Bayesian Decision Theory** Bayesian Decision Theory selects optimal actions by combining Bayesian calculations predicting future outcomes with utility or cost functions defining preferences for future plans. In contrast, Active Inference posits that priors directly signal what is valuable to an organism, optimizing beliefs by minimizing variational free energy and expected free energy. The Complete Class Theorem states that for any decision and cost function, there must exist a prior supporting a Bayes-optimal decision, meaning that when Bayesian Decision Theory separately handles priors and cost functions, it encounters issues of duality or degeneracy. Active Inference resolves this by integrating preferences directly.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/6.gif" style="width: 80%; height: auto;">
    <figcaption>
      Training process of a reinforcement learning agent using NVIDIA's Isaac Sim simulator. Source: <a href="https://pypi.org/project/rl-games/1.1.1/">RL Games, PYPI.</a>
    </figcaption>
  </figure>
</div>

**Reinforcement Learning** Reinforcement learning (RL) involves learning policies through trial-and-error, using rewards and value functions to select optimal actions. RL is divided into model-free methods that learn value functions directly, model-based methods that learn value functions and policies from model-generated data, and policy gradient methods that directly optimize policies without value functions. In contrast, Active Inference optimizes beliefs by minimizing variational and expected free energy instead of using rewards and value functions. RL assumes that actions are mediated through trial-and-error learning and reinforcement, while Active Inference assumes that actions result from inference. Additionally, RL sees goal-directed and habitual behaviors as corresponding to model-based and model-free RL, acquired in parallel and competing, while in Active Inference, habitual behaviors can be acquired by repeatedly pursuing goal-directed policies, allowing for cooperation.

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/7.png" style="width: 70%; height: auto;">
    <figcaption>
      Scholars who formalized the control and planning problems as probabilistic inference. Source: Personal presentation materials.
    </figcaption>
  </figure>
</div>

**Planning as Inference** Just as perception can be viewed as a problem of inference, so too can control and planning be seen as inference problems. This relates to ideas like Control As Inference by Rawlik and Levine, Planning As Inference by Attias, Botvinick, and Toussaint, and Risk-Sensitive, KL Control by Kappen. Active Inference and other "Planning as Inference" theories use dynamic generative models to encode probabilistic relationships between states and actions, inferring action sequences. However, they differ in three main dimensions: (1) inference method, (2) inference target, and (3) inference goal. Active Inference uses variational inference for scalable and efficient computation, infers posteriors over model-based planning, action sequences, or policies, and aims to minimize expected free energy for broader goals. Other theories use different inference methods like sampling, focus on individual actions or action sequences, and aim to maximize rewards.

### (5) Behavior and Bounded Rationality

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/8.jpg" style="width: 40%; height: auto;">
    <figcaption>
      Daniel Kahneman, Nobel laureate and founder of behavioral economics. Source: <a href="https://www.lowyinstitute.org/the-interpreter/daniel-kahneman-psychologist-who-shaped-economics-world">Lowy Institute</a>.
    </figcaption>
  </figure>
</div>

In Active Inference, deliberative, perseverative, and habitual aspects of behavior are automatically integrated. For example, when a person goes shopping, they create a deliberative plan to minimize expected free energy, maintain current behavior by minimizing variational free energy, and perform habitual actions based on past experiences. Unlike Kahneman's Dual System Theory, this suggests that deliberative, perseverative, and habitual behaviors coexist and cooperate depending on the situation. Deliberative actions vary with cognitive resources, which can carry complexity costs, and the concept of bounded rationality emphasizes balancing the costs, effort, and timeliness of computation. Active Inference views behavior as a result of inference, guiding optimal actions across diverse situations.

**Free Energy Theory and Bounded Rationality** Bounded Rationality is explained in terms of Helmholtz Free Energy Minimization, which relates to the concept of variational free energy used in Active Inference. It explains the trade-offs in action selection through the balance between energy/accuracy and entropy/complexity. In Active Inference, free energy is minimized through the trade-off between the cost of increasing precision and accuracy. The concept of bounded rationality resonates with Active Inference, which uses variational bounds to evaluate evidence. As a result, Active Inference offers a model of (bounded) rationality and optimality that finds the best solutions by balancing accuracy and complexity.

### (6) Valence, Emotion, and Motivation

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/9.png" style="width: 60%; height: auto;">
    <figcaption>
      The relationship between neuropsychology, cognitive neuroscience, behavioral neuroscience, and cognitive psychology, as outlined by Jaak Panksepp, founder of affective neuroscience. Source: <a href="https://www.psychologytoday.com/sites/default/files/attachments/109303/jcs-articlefinal.pdf">A Synopsis of Affective Neuroscience — Naturalizing the Mammalian Mind(2012), Jaak Panksepp</a>.
    </figcaption>
  </figure>
</div>

Active Inference uses (negative) free energy as a measure of an organism's ability to achieve its goals, with organisms adjusting their behavior by following the gradient without needing to know the free energy value itself. Emotional valence is explained as the rate of change in free energy over time, with decreases in free energy interpreted as positive valence and increases as negative valence. Moreover, higher-order derivatives can explain more complex emotional states; relief is described as the transition from high to low valence, while disappointment is the transition from low to high. This is related to precision, as it is the second derivative of free energy. Expectations of increases or decreases in free energy play a crucial role in motivation and action selection. The precision of beliefs about policies is linked to dopamine signals, where dopamine bursts can occur when a reliable policy is found. Understanding the neurophysiological mechanisms that connect expectations of achieving goals or rewards with increases in attention and motivation is anticipated.

### (7) Homeostasis, Allostasis, and Interoception

Active Inference maintains homeostasis by using generative models that explain and regulate an organism's internal milieu. It activates autonomic reflexes through interoceptive inference to regulate physiological parameters and uses allostatic strategies to minimize expected free energy, proactively preventing interoceptive prediction errors. Physiological regulation plays a key role in affective and emotional processing, with the flow of interoceptive information during external stimulus perception assigning affective meaning to situations. Emotional inference treats emotions as part of the generative model, updating beliefs and regulating behavior. For instance, anxiety is explained by the Bayesian belief "I am anxious," which accounts for sensory inputs and interoceptive signals, with such predictions adjusting precision or triggering autonomic responses. Typically, interoceptive and exteroceptive sensory information is integrated, with disease research showing a close relationship between emotion, interoception, and attention.

### (8) Attention, Salience, and Epistemic Dynamics

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/10.jpg" style="width: 60%; height: auto;">
    <figcaption>
      Attention and saliency maps in visual images highlighting key subjects. Source: <a href="https://www.geeksforgeeks.org/what-is-saliency-map/">GeeksForGeeks</a>.
    </figcaption>
  </figure>
</div>

Attention and salience are crucial concepts in psychology. In Active Inference, attention is defined as the precision of sensory input, and salience is defined as expected information gain or epistemic value. Attention is the selection of sensory data that has a greater influence on belief updating, while salience is the stimulus expected to provide more information; attention is the potential to infer, and salience is the potential to learn. Metaphorically, attention is the process of selecting the highest quality data from already measured data for hypothesis testing, while salience is the process of designing the next experiment to obtain the highest quality data. The formal approach of Active Inference resolves the ambiguity of attention and salience and explains why these two concepts are often confused. Epistemic dynamics describe how these concepts influence information acquisition and action decisions.

### (9) Rule Learning, Causal Inference, Rapid Generalization

<div class="centered-container">
  <figure>
    <img src="/assets/images/posts/2024/Q3/2024-08-03-Insights on Active Inference copy/11.jpg" style="width: 80%; height: auto;">
    <figcaption>
      Neuro-symbolic AI, a recent research program focusing on rule and symbol learning. Source: <a href="https://youtu.be/16X0RB_YrvE?si=4BMivbBypHkrlLhA">Presentation by Prof. Yison Yue at Caltech</a>.
    </figcaption>
  </figure>
</div>

The learning paradigm in Active Inference is based on developing generative models that capture causal relations between actions, events, and observations. Humans learn the latent structure of the environment through complex causal inference and generalization, contrasting with current machine learning approaches based on simple pattern recognition. Learning hidden rules allows for better predictions and generalization with fewer sensory details. This ability enables efficient learning in new situations and the development of a learning-to-learn capability. Active Inference emphasizes balancing accuracy and complexity in models, with model reduction being an effective method not only for preventing the waste of resources but also for learning hidden rules.

### (10) Other Applications

Beyond survival and adaptation, Active Inference can be applied to various fields, including social and cultural dynamics, machine learning, and robotics. In social and cultural dynamics, it explores the effects of interactions between agents. In machine learning and robotics, it studies learning mechanisms for solving more complex problems in ways compatible with the theory.

**Social and Cultural Dynamics** Human cognition is deeply intertwined with social and cultural dynamics rather than isolated individual cognition. Social dynamics, ranging from physical interactions like team sports to abstract interactions like elections, require interaction between multiple Active Inference agents. Simple simulations have already shown interesting emergent phenomena such as self-organization in simple life forms resisting extinction, morphogenetic processes acquiring and restoring body shapes, and mutual coordinated prediction and take-turning. These studies suggest that cognition extends beyond the skull into social niches. Active Inference has the potential to expand from the science of individuals to the science of societies.

**Machine Learning and Robotics** In machine learning and robotics, generative modeling and variational inference methods are widely used. Early connectionist generative models like the Helmholtz Machine and Boltzmann Machine provided methods for learning the internal representation of neural networks in an unsupervised manner, closely related to variational approaches. Recent models like Variational Autoencoders (VAEs) and Generative Adversarial Networks (GANs) are widely used for recognizing or generating images and videos. VAEs learn accurate descriptions of data while minimizing complexity, and GANs generate high-quality data through competition between generative and discriminative networks. Generative models are also used in high-dimensional movement control in robots, enabling learning through autonomous exploration, demonstration by humans, and interaction with humans. Active Inference provides an effective approach to addressing these challenges and contributes to the development of more advanced robotic technologies.

## Summary

> Daniel Dennett's criticism is valid. The traditional engineering problem-solving paradigm has focused on individually implementing sub-systems of cognitive functions, but the results have been far from achieving human-level artificial intelligence. Now, we must develop active inference agents based on a more comprehensive understanding of human and animal cognition. This approach will lead to more complex, energy-efficient, and effective technologies than simple system integration. Applying insights from neurobiology will enable the implementation of more sophisticated AI.

> Developing human-level AI requires not only technological innovation but also deep philosophical reflection on how that technology will impact our lives and society. While the Active Inference paradigm is normative and thus not scientifically falsifiable, it will play a crucial role in integrating diverse knowledge and discovering creative solutions.
