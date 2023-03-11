---
title: Artificial General Intelligence Safety Fundamentals Summary (2023 Cohort) - Part 1
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

# Week 0 (Optional): Introduction to ML

High level, machine learning (a subset of artificial intelligence) is giving a machine a method to which it may learn from data.
The current paradigm leverages mostly deep learning where the system is often shown millions of examples to generalize to
a sample of never-before-seen information (via a [train-dev-test split](https://cs230.stanford.edu/blog/split/) process).
In my view, generalization is among the most interesting aspects of ML as it is so difficult to do well. 
Humans are given a few examples and generalize rather easily. As of right now, AIs struggle to generalize (more in my Week 1 summary below).

Given that most of the latest research deploys deep learning, 
Ngo's diagram outlines Optimization techniques and Neural network architectures
where the [~2 hours of videos](./AGI-Safety-Program-Part-1#videos) cover both of these deep learning concepts in detail.
The most salient of these is the transformer as it has been demonstrated to learn context and be deployed in various use cases (such as text and images).

<img src="/assets/2021-ngo-ml-summary-diagram.png" alt="NgoSummary" width="512" class="center"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

Finally, Ngo breaks down ML tasks further toward the end of his post. 

<img src="/assets/2021-ngo-detailed-breakdown.png" alt="NgoDetails" width="512" class="center"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

# Week 1: Artificial General Intelligence

The Program officially begins with narrowing on the definition of Artificial General Intelligence [AGI].
"Intelligence measures an agent’s ability to achieve goals in a wide range of environments."
[Legg & Hutter 2.6 (2007)](https://ar5iv.labs.arxiv.org/html/0712.3329)
Legg & Hutter define intelligence mathematically in their paper but the vague intuition works well for the Program.
Steve Wozniak has the clever/cute
[Coffee Test](https://en.wikipedia.org/wiki/Artificial_general_intelligence#Tests_for_testing_human-level_AGI)
to determine whether a system possesses general intelligence. 

> A machine is required to enter an average American home and figure out how to make coffee: find the coffee machine, find the coffee, add water, find a mug, and brew the coffee by pushing the proper buttons.

Although AIs struggle right now with generalizing (and [other human capabilities](https://intelligence.org/2015/07/24/four-background-claims/)), 
I believe our uniqueness & intellectual superiority will _largely_ fade by the end of this century.
This forecast of "AGI is ~80% likely by the end of this century" (paraphrasing) comes from [Bio-anchors by Ajeya Cotra (2020)](https://www.alignmentforum.org/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines)
where 2021 Holden Karnofsky [summarizes where the "Experts" stand,](https://www.cold-takes.com/where-ai-forecasting-stands-today/)
and he concludes a ~2/3 chance by the end of this century. 
Cotra [updated](https://www.alignmentforum.org/posts/AfH2oPHCApdKicM4m/two-year-update-on-my-personal-ai-timelines)
her forecast in late 2022 with the median likelihood to be ~2040 now vs. ~2050 previously. 
By induction, I can assume that she also increased her ~80% forecast as well but am not able to say precisely. 
It is worth noting that these forecasts are to bound our expectations vs. seeing them as precise figures to defend.

<img src="/assets/2020-cotra-forecast.png" alt="Cotra2020FC" width="1024" class="center"/>

Given these timelines, I hope (and with modest confidence believe) we're in the [slow takeoff scenario](https://sideways-view.com/2018/02/24/takeoff-speeds/)
where we'll see continuous acceleration of technological progress. Practically speaking, I don't think 
there's much value in considering a fast takeoff scenario as we'd be unable to react to a superintelligent agent - more below.

Although the Program doesn't cover the various types of intelligent agents, I'd like to do so below for the most popular kinds:
- **Transformative AI [TAI]**: An AI that brings about a dramatically different future (roughly comparable but probably more significant than the agricultural or industrial revolution). [OpenPhil](https://www.openphilanthropy.org/research/some-background-on-our-views-regarding-advanced-artificial-intelligence/#:~:text=Roughly%20and%20conceptually%2C%20transformative%20AI,the%20agricultural%20or%20industrial%20revolution.)
- **Artificial General Intelligence [AGI]**: An AI that's broadly capable of most/all functions that an animal can do. We are still within the scale what we can comprehend as intellectuals have created a rough intuitive scale of ants, bees, crows, and humans. We're quickly scaling up the ladder as artificial minds become more and more capable.
   - Fun fact: Orangutans, pigs, and octopi are among the smartest, less well-known animals (most think of chimps, dolphins, or mice first). [Longer list](https://thehumaneleague.org/article/animal-intelligence)   
- **Seed AI**: An AGI that recursively rewrites its own source code without human intervention. [Yudkowsky (2007)](http://intelligence.org/files/LOGI.pdf)
- **Superintelligent AI**: An agent that far surpasses the brightest human minds both individually and even what can be done collectively. If the Manhattan Project was the combination of the brightest minds, a superintelligent agent would view them as intellectually equal as we view ants (but probably even more inferior in this axis if my anthropological lens is true in the first place).
   - In my view, an AGI will very likely become a superintelligent agent. We'd need to bound the AGI or rethink how we design AI systems. Bostrom explores several boxing methods in his book that aren't all that promising and suggests of coming up with novel ways to ensure that a Seed AI has certain values "pre-loaded."

The ordering above has a feeling of increasing levels of complexity or impressiveness. 
A lighter version is explored in several candid/hopeful short stories in Kai-Fu Lee's **AI 2041.** 
He describes _realistic AI,_ or "technologies that either already exist 
or can be reasonably expected to mature within the next twenty years."
Lee and others seem skeptical of TAI happening this century. 
I think the best resource pushing back on this view is from
[All Possible Views About Humanity's Future Are Wild.](https://www.cold-takes.com/all-possible-views-about-humanitys-future-are-wild/)
In this post Karnofsky explores this conservative view by steelmanning various timelines of 100, 500, and even 100,000 years.
For galaxy-scale timelines these 100-100,000 year gaps would converge on the same pixel in the visual below. 
Granted the level of urgency would (thankfully) lift from our shoulders, but we'd still be among a tiny group of people placed in an important time period.
In other posts Karnofsky expands on the idea that AI alignment is challenging and many problems remain unsolved.
The rest of the Program focuses on the various problems/issues that emerge.   

<img src="/assets/2021-karnofsky-cosmic-endowment.png" alt="Karnofsky2021Cosmic" width="1012"/>

_[Image from Cold Takes](https://www.cold-takes.com/forecasting-transformative-ai-the-biological-anchors-method-in-a-nutshell/)_

# Week 2: Reward misspecification and instrumental convergence

I've included my shortened versions of Nick Bostrom's "Orthogonality Thesis" & Steve Omohundro's "Instrumental convergence" (later expanded by Bostrom) 
from [my "Why AGI?" post.](https://mitchell-reynolds.github.io/Why-AGI#beliefs--arguments)

> 1. **Orthogonality Thesis**: Intelligence and final goals can be two different axes within an AGI. Therefore, the space of possibilities includes "Superintelligence, Misaligned with Human Goals."
> 2. An AGI being misaligned to human values seems more likely than to be aligned. This is because by-and-large the AGI will seek power (almost always an **instrumental goal**) to accomplish its terminal or final goal.
> 3. Even if the above two are solved, it is still possible for an AGI to create a terrible outcome that results from the **value loading problem.**
>    - Using the example goal of "cure cancer" to an AGI: the AGI _could_ solve for this by giving everyone a pill where they die at the age of 40. The AGI found that cancer is much more common in old age and solved the goal given but is not aligned with human values.

TODO

**Specification gaming** is a behaviour that satisfies the literal specification of an objective
without achieving the intended outcome with a 
[combined list of examples.](https://docs.google.com/spreadsheets/d/e/2PACX-1vRPiprOaC3HsCf5Tuum8bRfzYUiKLRqJmbOoC-32JorNdfyTiRRsR7Ea5eWtvsWzuxo8bjOxCG84dAg/pubhtml)
[Deepmind (2020)](https://www.deepmind.com/blog/specification-gaming-the-flip-side-of-ai-ingenuity)

# Week 3: Goal misgeneralization

# Footnotes [PLACEHOLDER]

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
- [[Video] Inverse reinforcement learning example (2016)](https://www.youtube.com/watch?v=h7uGyBcIeII)
- [The easy goal inference problem is still hard (2018) by Paul Christiano](https://www.alignmentforum.org/s/4dHMdK5TLN6xcqtyc/p/h9DesGT3WT9u2k7Hr)
- [[Advanced ML] Optimal Policies Tend To Seek Power (2021) by Alex Turner et alia](https://neurips.cc/virtual/2021/poster/28400)

---

## Materials for Week 3: Goal misgeneralization [~95 minutes]
- [Goal misgeneralization: why correct specifications aren’t enough for correct goals (2022) by Rohin Shah et alia](https://ar5iv.labs.arxiv.org/html/2210.01790)
- [[Video] The other alignment problem: mesa-optimisers and inner alignment (2021)](https://youtu.be/bJLcIBixGj8)
- [Why alignment could be hard with modern deep learning (2021) by Ajeya Cotra](https://www.cold-takes.com/why-ai-alignment-could-be-hard-with-modern-deep-learning/)
- [What failure looks like (2019) by Paul Christiano](https://www.alignmentforum.org/posts/HBxe6wdjxK239zajf/what-failure-looks-like)
- [[Advanced ML] Thought Experiments Provide a Third Anchor (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/thought-experiments-provide-a-third-anchor/)
- [[Advanced ML] ML Systems Will Have Weird Failure Modes (2022) by Jacob Steinhardt](https://bounded-regret.ghost.io/ml-systems-will-have-weird-failure-modes-2/)
- [[Advanced ML]The alignment problem from a deep learning perspective (2022) by Richard Ngo et alia](https://ar5iv.labs.arxiv.org/html/2209.00626)