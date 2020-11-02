---
layout: post

title: Codistillation for Distributed Training

abstract: This work contributes to a better understanding of codistillation and how to best take advantage of it in a distributed computing environment.

---

**Speaker:** <a href="https://shagunsodhani.com/" target="_blank">Shagun Sodhani</a>, Research Engineer at Facebook AI Research, Masters in Artificial Intelligence (Université de Montréal), Btech in Computer Science and Engineering (IIT Roorkee). <br>


##### Part 1: Research talk (25min)

**Topic**: Distributed Training of Neural Networks <br>
**Title**: Codistillation for distributed training <br>
**Abstract**: Codistillation has been proposed as a mechanism to share knowledge among concurrently trained models by encouraging them to represent the same function through an auxiliary loss. This contrasts with the more commonly used fully-synchronous data-parallel stochastic gradient descent methods, where different model replicas average their gradients (or parameters) at every iteration and thus maintain identical parameters. We investigate codistillation in a distributed training setup, complementing previous work which focused on extremely large batch sizes. Surprisingly, we find that even at moderate batch sizes, models trained with codistillation can perform as well as models trained with synchronous data-parallel methods, despite using a much weaker synchronization mechanism. These findings hold across a range of batch sizes and learning rate schedules, as well as different kinds of models and datasets. Obtaining this level of accuracy, however, requires properly accounting for the regularization effect of codistillation, which we highlight through several empirical observations. Overall, this work contributes to a better understanding of codistillation and how to best take advantage of it in a distributed computing environment.<br>

##### Part2: Ask me anything (25min)

**Bio**: His research interest is in lifelong reinforcement learning -- training AI systems that can interact with and learn from the physical world and consistently improve as they do so without forgetting the previous knowledge. Previously, he was a graduate student at MILA (advised by Dr Jian Tang and Dr Yoshua Bengio)<br>

<!--**Slide:** [Link](https://drive.google.com/file/d/1bvzZSB9BrHcEV0idbWQN_oo45o1zfdLg/view?usp=sharing) <br>-->
**Video:** [Youtube](https://www.youtube.com/watch?v=pBt0S221QRA&feature=youtu.be) <br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/-e1ncUd1R9w" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
