
# Current Research

My current work focuses on using principles from optimal control to improve the generalization capabilities of AI models. Specifically, **generative diffusion models** and **deep unfolded algorithms** can both be described as controlled dynamical systems. From this perspective, the ability of these models to generalize beyond their training data corresponds can be formulated as the robustness of the controlled system. Therefore, nonlinear optimal control provides a principled framework to derive new methods to quantify model performance and improve their ability to generalize.

## The Role of Feedback in Schrödinger Bridge Diffusion Models

**Schrödinger bridge model** (SBMs) are a state-of-the-art diffusion model that generalize common models, such as denoising diffusion probabilistic models (DDPMs). Methods like DDPMs operate by incrementally adding noise to a data set and then learning to undo this process. New samples from random noise can then be used to produce *new* data, such as images. SBMs generalize this approach by finding a dynamical system that transforms one distribution to another. Unlike DDPMs, very few assumptions are placed on these distributions --- each can be known *a priori* as a modeling assumption or come from data. This problem is naturally framed as a kind of stochastic optimal control problem known as an *optimal transport* problem.

Thus far, I have worked on how using feedback control can be used to improve SBMs in a semi-supervised setting, where a few data points from each distribution are labeled as pairs. Prior work largely considers finding controls that drive data from one distribution to another in an open-loop manner which works well for large datasets. However, when the labeled data is limited, there is no guarantee a sample that starts near a labeled data point remains close to that data point at the end of the process. We address this issue by instead learning **closed-loop controls** to evolve samples, which guarantee neighborhoods around labeled points remain close. This method empirically improves both the generative quality of the learned model in low-data regimes and reduces computational requirements in large data regimes.

Presently, I am working on formalizing the benefits using **PAC-Bayes control methods** as well as how these methods can be used beyond popular applications, like image generation and transformation, to learn **models of physical systems** from data. Usecases include **imitation learning** and **AI-for-science** applications.

## Certifying and Improving the Performance of Deep Unfolded Optimizers

A **deep unfolded algorithm** is a kind of neural network that replaces the nonlinearities commonly found in the deep learning literature with a parameterized step of an algorithm. A simple example is gradient descent: the gradient of an objective function provides a nonlinearity and the stepsize provides a parameter to be learned. Subsequently, optimization methods and other iterative algorithms can be fine-tuned using data generated from tasks of interest, such as model-predictive control problems for a robot. 

Recognizing that a deep unfolded algorithm is a **discrete-time control system**, where control is the algorithm parameter, a further step can be taken by making the algorithm parameters state-dependent, i.e., specifying these parameters via **feedback control**. Using this framework, I used methods from PAC-Bayes control to design a method for learning deep unfolded algorithms with proven performance guarantees. This method was used to certify that a new *distributed deep unfolded QP solver* designed by my colleague outperforms classical optimizers once it is trained. Moreover, this method produces a special regularizer which empirically improves the generalization of the learned algorithm. 

# Past Projects
My dissertation work focused on studying the role of **task-relevant information** in robot control problems, the theoretical benefits of making control decisions using only task-relevant information, algorithmically designing these controllers, and how much task-relevant information a sensor *must* provide to achieve performant control.

## Task-Relevancy and Bounded Rationality Robots

<img class="img-fluid photo" src="assets/images/bottleneck.svg" style="width: 60%; float: right; padding-left: 2.5%; padding-bottom: 2.5%; padding-top: 2.5%;">

Today, robots are equipped with powerful, high-dimensional, general-purpose sensors (e.g., cameras), which allow general purpose control algorithms to achieve high performance on many challenging tasks. However, the generic nature of these algorithms requires that large amounts of sensor information is processed regardless of whether or not it is relevant to the robot's task, and disturbances irrelevant components of the sensor observation can significantly degrade the performance of the closed-loop system.

In contrast, humans are equipped with powerful, high-dimensional, general-purpose, sensors (e.g., our eyes) but they rely on *task-relevant heuristics* to perform dexterous tasks, like ball-catching, robustly by monitoring only a few **task-relevant variables** that capture most of important information. This kind of limited, but effective decision-making is known as employing **bounded rationality**. My work in this area has focused on algorithmically identifying the (often low-dimensional) task-relevant variables in optimal control problems, designing controllers that depend on these variables only, and demonstrating the performance-robustness tradeoffs of these controllers. These goals are achieved through an approach using overlapping tools from fields such as, **information theory**, **statistical mechanics**, and **differential privacy** in conjunction with experiments in simulation and on real hardware platforms.

## Fundamental Limits in Sensing and Control for Robotics

<img class="img-fluid photo" src="assets/images/trip.svg" style="width: 60%; float: right; padding-left: 2.5%; padding-bottom: 2.5%; padding-top: 2.5%;">

Some of my recent work has been on understanding **fundamental limits** on the performance achievable by a robot equipped with different sensors on an optimal control problem. The aim is to answer questions such as: does an autonomous car require different sensing modalities, or is a vision system enough? In principle, if both systems capture the relevant information for the task, then the cost of sensing and processing additional information does not yield a meaningful increase in performance.

Establishing such limits is largely an open problem in robotics. My work makes early steps toward answering this question by deriving estimatable lower-bounds on control cost in terms of the information a sensor may provide using emerging techniques in information theory (e.g., new generalizations of Fano's inequality) and non-equilibrium thermodynamics.