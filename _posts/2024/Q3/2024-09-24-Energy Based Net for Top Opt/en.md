<!-- ---
title: "Shape Optimization Using Energy-Based Networks"
scope:
  type: posts
values:
  layout: single
  author_profile: true
  read_time: true
  comments: true
  share: true
  related: true
toc: false
category: Meditation
tags: [ideas, shape optimization, optimal design, energy-based networks, Hopfield network]
lang: en
header:
  teaser: "/assets/images/posts/2024/Q3/2024-09-24-Energy Based Net for Top Opt/TopOpt of a Compliance Prob.png"
image: /assets/images/posts/2024/Q3/2024-09-24-Energy Based Net for Top Opt/TopOpt of a Compliance Prob.png
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


A while ago, I read [Max Tegmark's Life 3.0](https://www.amazon.com/Life-3-0-Being-Artificial-Intelligence/dp/1101946598), where he introduces the concept of an ultimate life form capable of modifying not only its software but also its hardware. More recently, I came across an idea: what if we could use energy-based networks, particularly the [Hopfield Network](https://en.wikipedia.org/wiki/Hopfield_network), to perform [shape/topology optimization](https://en.wikipedia.org/wiki/Topology_optimization)? In Hopfield Networks, the weights between nodes are adjusted to minimize the system’s total energy. If these weights represent a **physical meaning**, such as the *distance between nodes*, then perhaps the process of minimizing energy in the network could help us discover the optimal physical shape.



<div class="centered-container">
  <div class="two-fig-container">
    <figure>
      <img src="/assets/images/posts/2024/Q3/2024-09-24-Energy Based Net for Top Opt/Memory Retrieval in Hopfield Network .gif" style="width: 60%; height: auto;">
      <figcaption>
        Visualization of How Hopfield Network Works, 출처: <a href="https://towardsdatascience.com/visualizing-episodic-memory-with-hopfield-network-a6e8bde967cb">Muhammad Abduh</a>.
      </figcaption>
    </figure>
    <figure>
      <img src="/assets/images/posts/2024/Q3/2024-09-24-Energy Based Net for Top Opt/Scheme for Hopfield Network.png" style="width: 55%; height: auto;">
      <figcaption>
        Energy landscape of a Hopfield Network, 출처: <a href="https://www.researchgate.net/figure/Illustration-of-a-Hopfield-network-with-transiently-chaotic-dynamics-A-Schematic-of-a_fig1_343660391">Ke Yang et al(2020).</a>
      </figcaption>
    </figure>
  </div>
</div>

However, there are a few challenges with this approach. In a fully connected Hopfield Network, all nodes are interconnected. If we interpret the weights as the Euclidean distances between nodes, not every combination of weights will correspond to a shape that can be realized in 2D or 3D space. This is because the given distances might not satisfy the geometric constraints of Euclidean space, such as the triangle inequality.

For example, let’s say we have three nodes with distances between them defined as $w_{1,2}=1$, $w_{1,3}=3$, and $w_{2,3}=2$. In this case, it’s possible to determine their positions in 2D space. But if we add a fourth node with distances $w_{1,4}=2$, $w_{2,4}=3$, and $w_{3,4}=1$, finding a position for this fourth node that satisfies all these distances in 2D becomes impossible.

To address this, several approaches can be considered:

Increasing the embedding dimension: One way to determine a 3D shape is by checking the positive semidefiniteness of the weight matrix (or distance matrix). This ensures that the given distances are valid in Euclidean space. If positive semidefiniteness is satisfied, we can position the nodes in a higher-dimensional space, allowing us to meet the distance constraints.

Redesigning the energy function: By redesigning the energy function, we can incorporate physical constraints and shape realizability, ensuring that the network learns to generate realistic shapes during the optimization process.

Adjusting distances or allowing for error: We could slightly modify the given distances or minimize the error between the distances and the actual positions of the nodes. This would introduce a necessary compromise to obtain a feasible shape.

Multidimensional Scaling (MDS): MDS can be used to find node positions based on the given distance data while minimizing discrepancies between the distances and their corresponding node positions.

Integrating physical constraints: By integrating physical constraints into the energy function, we can guide the network toward producing shapes that reflect the physical properties of the structure, leading to more practical results.

Additional considerations include:

Redesigning the physical energy function: The energy function can be adapted to incorporate actual physical system properties, allowing the network to adjust the weights in a way that directly relates to shape optimization.

Data-driven approaches: Collecting data on real-world shapes and their corresponding weights can allow the network to learn the complex relationships between weights and shape through supervised learning.

Utilizing GPU-based parallel processing: Solving large-scale optimization problems efficiently requires leveraging the parallel processing capabilities of GPUs. Frameworks like TensorFlow or PyTorch can be used to accelerate these tasks.

In conclusion, interpreting weights as physical distances and applying energy-based neural networks to shape optimization is a fascinating idea. However, for practical implementation, it’s necessary to model the relationship between weights and physical shapes more accurately, taking into account the geometric constraints and physical properties. By doing so, innovative methods for shape optimization could be developed using neural networks.

Future research directions include:

Exploring the intersection of topology optimization and deep learning: Investigating existing research can help refine ideas and discover new approaches.

Studying optimization algorithms and mathematical tools: Learning about nonlinear optimization, graph embedding, and multidimensional scaling can improve the accuracy of models.

Combining physical simulation: Integrating finite element analysis (FEA) tools with neural networks can help verify and improve the accuracy of predictions.

Pursuing research in these directions could yield meaningful results in applying energy-based networks to shape optimization. Additionally, [**studies on topology optimization using Cellular Automata**](https://www.mdpi.com/2076-3417/13/5/2929) have also emerged. Considering such approaches could lead to the development of practical technologies. -->
