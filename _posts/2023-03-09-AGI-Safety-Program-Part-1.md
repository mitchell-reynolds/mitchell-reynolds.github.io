---
title: AGI Safety Fundamentals Summary - Part 1
published: true
categories:
- agi
---

# Background, Context, & Goals
This is the first installment of my summary & extrapolations for the 
Artificial General Intelligence Safety Fundamentals Program [Program] offered by 
[BlueDot,](https://www.agisafetyfundamentals.com/) which spun out of 
[Effective Altruism Cambridge](https://www.eacambridge.org/) in collaboration with
[Richard Ngo.](https://www.richardcngo.com/)
My involvement with the Program began in 2021 where I started as a participant facilitated by Michael Chen. 
In 2022 and 2023, I was offered to be a paid facilitator for 1 cohort each iteration. 

My goals for facilitating & writing these summaries are to:
1. Improve participants' & readers' understanding on this important topic.
2. Establish connections with those also interested in contributing to the AI alignment problem.
   - Connections (Direct work): Either these folks will be future colleagues or will have overlap in the field of AI alignment. In my view, I believe most industries will be impacted by the advancements of AI.
   - Connections (Indirect work): As most participants are technical, I can see a future where SWE/researchers are working for any of the [MAMAA](https://fortune.com/2021/10/29/faang-mamaa-jim-cramer-tech-facebook-meta/) companies and could be part of the capabilities frontier. I believe that capabilities SWE/researchers should be knowledgeable about AGI safety.
3. Improve, clarify, & solidify my own understanding around this challenging topic while also staying up to date on the latest research.
4. Practice my oral & written communication skills for AGI safety information and to ["find ways to help people understand the core parts of the challenges we might face, in as much detail as is feasible."](https://www.cold-takes.com/spreading-messages-to-help-with-the-most-important-century/)
5. [Bonus] Establish myself as a credible & properly nuanced source of AGI safety knowledge.
6. [Bonus] By staying up-to-date on the latest research, directly contribute to the advancement of ["helpful, honest, and harmless"](https://ar5iv.labs.arxiv.org/html/2112.00861) AI systems with a focus on strategy.

# Week 0: Introduction to ML

High level, machine learning (a subset of artificial intelligence) is giving a machine a method to which it may learn from data.
The current paradigm leverages mostly deep learning where the system is often shown millions of examples to generalize to
a sample of never-before-seen information (aka [train-dev-test split](https://cs230.stanford.edu/blog/split/)).
In my view, generalization is among the most interesting aspects of ML as it is so difficult to do well. 
Humans are given a few examples and generalize rather easily. As of right now, AIs struggle to generalize (more in my Week 1 summary below).

Given that most of the latest research deploys deep learning, 
Ngo's diagram outlines Optimization techniques and Neural network architectures
where the [~2 hours of videos](./AGI-Safety-Program-Part-1#videos) cover both in detail.
The most salient of these is the transformer as it has been demonstrated to learn context and be deployed in various use cases (such as text and images).

<img src="/assets/2021-ngo-ml-summary-diagram.png" alt="NgoSummary" width="540"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

Finally, Ngo breaks down ML tasks further toward the end of his post. 

<img src="/assets/2021-ngo-detailed-breakdown.png" alt="NgoDetails" width="540"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

# Week 1: Artificial General Intelligence

The Program officially begins with narrowing on the definition of Artificial General Intelligence [AGI].
"Intelligence measures an agent’s ability to achieve goals in a wide range of environments."
[Legg & Hutter 2.6 (2007)](https://ar5iv.labs.arxiv.org/html/0712.3329)
Legg & Hutter define intelligence mathematically in their paper but the vague intuition works well for the Program.
Steve Wozniak has the clever/cute
[Coffee Test](https://en.wikipedia.org/wiki/Artificial_general_intelligence#Tests_for_testing_human-level_AGI)
to determine whether a system possesses general intelligence. 

"""
A machine is required to enter an average American home and figure out how to make coffee: find the coffee machine, find the coffee, add water, find a mug, and brew the coffee by pushing the proper buttons.
"""

Although AIs struggle right now with generalizing (and [other human capabilities](https://intelligence.org/2015/07/24/four-background-claims/)), 
I believe our uniqueness & intellectual superiority will _largely_ fade by the end of this century.
This forecast of "AGI is ~80% likely by the end of this century" comes from [Bio-anchors by Ajeya Cotra (2020)]()
where 2021 Holden Karnofsky [summarizes where the "Experts" stand](https://www.cold-takes.com/where-ai-forecasting-stands-today/)
and concludes a ~2/3 chance by the end of this century. 
Cotra [updated](https://www.alignmentforum.org/posts/AfH2oPHCApdKicM4m/two-year-update-on-my-personal-ai-timelines)
her forecast in late 2022 with the median likelihood to be ~2040 now vs. ~2050 previously.

# Week 2: Reward misspecification and instrumental convergence

# Week 3: Goal misgeneralization

# Links to Materials [~7 hours]

_I made a [Spotify Playlist](https://open.spotify.com/playlist/4RV5q7Z49XZflV38NoahF5?si=2567ed53d3944784) for the 
2022 iteration of the Program with **some** of the readings that should be viewed as supplemental and not as a substitution._ 

## Materials for Week 0: Introduction to ML [~165 minutes]
### Readings
- [A short introduction to machine learning by Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)
- [Machine Learning for Humans (2017) by Vishi Maini and Sabri](https://medium.com/@v_maini/supervised-learning-740383a2feab)

### Videos
- [But what is a neural network (2017)](https://www.youtube.com/watch?v=aircAruvnKk)
- [Gradient descent, how neural networks learn (2017)](https://www.youtube.com/watch?v=IHZwWFHWa-w)
- [What is backpropagation really doing? (2021)](https://www.youtube.com/watch?v=Ilg3gGewQ5U)
- [What is self-supervised learning? (2021)](https://youtu.be/sJzuNAisXHA)
- [Introduction to reinforcement learning (2021)](https://www.youtube.com/watch?v=TCCjZe0y4Qc&list=PLqYmG7hTraZDVH599EItlEWsUOsJbAodm)
- [Transformers, explained: Understand the model behind GPT, BERT, and T5 (2021)](https://www.youtube.com/watch?v=SZorAJ4I-sA)

---

## Materials for Week 1: Artificial General Intelligence [~95 minutes]
- [Visualizing the deep learning revolution (2023) by Richard Ngo](https://medium.com/@richardcngo/visualizing-the-deep-learning-revolution-722098eb9c5)
- [On the opportunities and risks of foundation models (2022) by Bommasani et alia](https://arxiv.org/pdf/2108.07258.pdf)
- [Four Background Claims (2015) by Nate Soares](https://intelligence.org/2015/07/24/four-background-claims/)
- [AGI safety from first principles (2020) by Richard Ngo](https://drive.google.com/file/d/1uK7NhdSKprQKZnRjU58X7NLA1auXlWHt/view)
- [[Video] Why and how of scaling large language models (2022) by Nicholas Joseph](https://www.youtube.com/watch?v=qscouq3lo0s)
- [Biological Anchors: A Trick That Might Or Might Not Work (2022) by Scott Alexander](https://astralcodexten.substack.com/p/biological-anchors-a-trick-that-might)
- [Intelligence explosion: evidence and import (2012) by Luke Muehlhauser and Anna Salamon](https://drive.google.com/file/d/1QxMuScnYvyq-XmxYeqBRHKz7cZoOosHr/view?usp=sharing)
- [[Advanced ML] Future ML Systems Will Be Qualitatively Different (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/future-ml-systems-will-be-qualitatively-different/)
- [[Advanced ML] More Is Different for AI (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/more-is-different-for-ai/)

---

## Materials for Week 2: Reward misspecification and instrumental convergence [~80 minutes]
- [Specification gaming: the flip side of AI ingenuity (2020) by Victoria Krakovna et alia](https://www.deepmind.com/blog/specification-gaming-the-flip-side-of-ai-ingenuity)
- [Learning from Human Preferences (2017) by Paul Christiano, Alex Ray and Dario Amodei](https://openai.com/blog/deep-reinforcement-learning-from-human-preferences/)
- [Learning to Summarize with Human Feedback (2020) by Jeffrey Wu et alia](https://openai.com/blog/learning-to-summarize-with-human-feedback/)
- [The alignment problem from a deep learning perspective (2022) by Richard Ngo et alia](https://ar5iv.labs.arxiv.org/html/2209.00626)
- [Superintelligence: Instrumental convergence (2014) by Nick Bostrom](https://drive.google.com/file/d/1KewDov1taegTzrqJ4uurmJ2CJ0Y72EU3/view?usp=sharing)
- [[Video]Inverse reinforcement learning example (2016)](https://www.youtube.com/watch?v=h7uGyBcIeII)
- [The easy goal inference problem is still hard (2018) by Paul Christiano](https://www.alignmentforum.org/s/4dHMdK5TLN6xcqtyc/p/h9DesGT3WT9u2k7Hr)
- [[Advanced ML] Optimal Policies Tend To Seek Power (2021) by Alex Turner et alia](https://neurips.cc/virtual/2021/poster/28400)

---

## Materials for Week 3: Goal misgeneralization [~95 minutes]
- [Goal misgeneralization: why correct specifications aren’t enough for correct goals (2022) by Rohin Shah et alia](https://ar5iv.labs.arxiv.org/html/2210.01790)
- [[Video]The other alignment problem: mesa-optimisers and inner alignment (2021)](https://youtu.be/bJLcIBixGj8)
- [Why alignment could be hard with modern deep learning (2021) by Ajeya Cotra](https://www.cold-takes.com/why-ai-alignment-could-be-hard-with-modern-deep-learning/)
- [What failure looks like (2019) by Paul Christiano](https://www.alignmentforum.org/posts/HBxe6wdjxK239zajf/what-failure-looks-like)
- [[Advanced ML] Thought Experiments Provide a Third Anchor (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/thought-experiments-provide-a-third-anchor/)
- [[Advanced ML] ML Systems Will Have Weird Failure Modes (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/ml-systems-will-have-weird-failure-modes-2/)
- [[Advanced ML]The alignment problem from a deep learning perspective (2022) by Richard Ngo et alia](https://ar5iv.labs.arxiv.org/html/2209.00626)