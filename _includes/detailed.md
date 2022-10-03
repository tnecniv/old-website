
# Research Overview
My research to date has focused on studying the role of **task-relevant information** in control problems, the theoretical benefits of making control decisions using only task-relevant information, algorithmically designing these controllers, and how much task-relevant information a sensor *must* provide to achieve performant control.

## Task-Relevancy and Bounded Rationality Robots

<img class="img-fluid photo" src="assets/images/bottleneck.svg" style="width: 60%; float: right; padding-left: 2.5%; padding-bottom: 2.5%; padding-top: 2.5%;">

Today, robots are equipped with powerful, high-dimensional, general-purpose sensors (e.g., cameras), which allow general purpose control algorithms to achieve high performance on many challenging tasks. However, the generic nature of these algorithms requires that large amounts of sensor information is processed regardless of whether or not it is relevant to the robot's task, and disturbances irrelevant components of the sensor observation can significantly degrade the performance of the closed-loop system.

In contrast, humans are equipped with powerful, high-dimensional, general-purpose, sensors (e.g., our eyes) but they rely on *task-relevant heuristics* to perform dexterous tasks, like ball-catching, robustly by monitoring only a few **task-relevant variables** that capture most of important information. This kind of limited, but effective decision-making is known as employing **bounded rationality**. My work in this area has focused on algorithmically identifying the (often low-dimensional) task-relevant variables in optimal control problems, designing controllers that depend on these variables only, and demonstrating the performance-robustness tradeoffs of these controllers. These goals are achieved through an approach using overlapping tools from fields such as, **information theory**, **statistical mechanics**, and **differential privacy** in conjunction with experiments in simulation and on real hardware platforms.

## Fundamental Limits in Sensing and Control for Robotics

<img class="img-fluid photo" src="assets/images/trip.svg" style="width: 60%; float: right; padding-left: 2.5%; padding-bottom: 2.5%; padding-top: 2.5%;">

Some of my recent work has been on understanding **fundamental limits** on the performance achievable by a robot equipped with different sensors on an optimal control problem. The aim is to answer questions such as: does an autonomous car require different sensing modalities, or is a vision system enough? In principle, if both systems capture the relevant information for the task, then the cost of sensing and processing additional information does not yield a meaningful increase in performance.

Establishing such limits is largely an open problem in robotics. My work makes early steps toward answering this question by deriving estimatable lower-bounds on control cost in terms of the information a sensor may provide using emerging techniques in information theory (e.g., new generalizations of Fano's inequality) and non-equilibrium thermodynamics.

# Future Interests

I have a growing interest in the interplay between fundamental problems in robotics and the natural sciences. Problems in natural sciences lead to the development of many useful theoretical tools and modeling formalisms for describing fundamental problems in these fields. Robotics, as a comparatively young discipline formed from the intersection between engineering, computer science, and other fields, is still searching for the right formalism to describe its unique problems. Adapting tools from the natural science broaden the vocabulary of the field and deepen our understanding of robotics.