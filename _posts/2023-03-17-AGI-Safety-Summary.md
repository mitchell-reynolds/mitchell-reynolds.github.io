---
title: AGI Safety Summary (Q1 2023 Cohort)
published: true
categories:
- agi
---

# Background, Context, & Goals 📚
This is the first installment of my summary & extrapolations for the 
Artificial General Intelligence Safety Fundamentals Alignment Course ("Course" hereafter) offered by 
[BlueDot,](https://www.agisafetyfundamentals.com/) which spun out of 
[Effective Altruism Cambridge](https://www.eacambridge.org/) in collaboration with
[Richard Ngo](https://www.richardcngo.com/) from OpenAI/DeepMind.
In total, the Course is expected to take ~30 hours taking place over 8 weeks with pre-readings & discussions and includes a self-guided project.

Although I have [~1000s hours of AI/ML training](./Why-AGI#ai-training-1000s-of-hours),
the Course begins with an optional Week 0 that takes ~2 hours to get up to speed conceptually.
I will assume this (admittedly small) audience has this level of familiarity and
that these summaries gloss over those preliminary details.
Instead, the focus will be the core 8 weeks of content with the occasional detour into "what it's like inside my mind."
Lastly, my involvement with the Course began in 2021 where I started as a participant led by Michael Chen.
In both 2022 & 2023, I was offered to be a paid facilitator for 1 cohort each iteration.

## Instrumental Goals
My instrumental goals for facilitating the Course & independently writing these summaries are to:
1. Distill ~30 hours of readings & discussions into ~30 minutes of reading here.
   - 30 minute estimate = ~6k words at [200 WPM](./Human-Info-Speed#reading--speaking-speeds)
2. Improve, clarify, & solidify my own understanding around this challenging topic while also staying up to date on the latest research.
3. Practice my communication skills for AI safety information and to "find ways to help people understand the core parts of the challenges we might face, in as much detail as is feasible." [[Cold Takes]](https://www.cold-takes.com/spreading-messages-to-help-with-the-most-important-century/)
4. Establish connections with those also interested in working in AI safety.
   - Connections (Direct work): Either these folks will be future colleagues or will have overlap in the field of AI safety. In my view, I believe most industries will be impacted by the advancements of AI.
   - Connections (Indirect work): As most participants are technical, I can see a future where SWE/researchers are working for any of the [MAMAA](https://fortune.com/2021/10/29/faang-mamaa-jim-cramer-tech-facebook-meta/) companies and could be part of the capabilities frontier. I believe that capabilities SWE/researchers should be knowledgeable about AI safety.
5. [Bonus] Establish myself as a credible & properly nuanced source of AI safety knowledge.
6. [Bonus] By staying up-to-date on the latest research, directly contribute to the advancement of ["helpful, honest, and harmless"](https://ar5iv.labs.arxiv.org/html/2112.00861) AI systems with a focus on strategy.

_My final goals are [here.](./about#purpose-lifelong) Lastly, I would like to thank Greg Tracy & my cat [Bunny](./assets/2022-Bunny.jpg) for feedback where all the mistakes are my own or Bunny's suggestions from walking on the keyboard._🐈

# Week 0 (Optional): Introduction to ML

High level, machine learning (a subset of artificial intelligence) is giving a machine a method to which it may learn from data.
The current paradigm leverages mostly deep learning where the system is often shown millions of examples to generalize to
a sample of never-before-seen information (via a [train-dev-test split](https://cs230.stanford.edu/blog/split/) process).
In my view, generalization is among the most interesting aspects of ML as it is so difficult to do well. 
Humans are given a few examples and generalize rather easily. As of right now, AIs struggle to generalize (more in my Week 1 summary below).

Given that most of the latest research deploys deep learning, 
Ngo's diagram outlines Optimization techniques and Neural network architectures
where the [~2 hours of videos](./AGI-Safety-Summary-Part-1#videos) cover both of these deep learning concepts in detail.
The most salient of these is the transformer as it has been demonstrated to learn context and be deployed in various use cases (such as text and images).

<img src="/assets/2021-ngo-ml-summary-diagram.png" alt="NgoSummary" width="1024" class="center"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

Finally, Ngo breaks down ML tasks further toward the end of his post. 

<img src="/assets/2021-ngo-detailed-breakdown.png" alt="NgoDetails" width="1024" class="center"/>

_Diagram by [Richard Ngo (2021)](https://www.alignmentforum.org/posts/qE73pqxAZmeACsAdF/a-short-introduction-to-machine-learning)_

# Week 1: Artificial General Intelligence 🤖

## Intelligence
The Course first better defines intelligence and, in particular, Artificial General Intelligence [AGI].
"Intelligence measures an agent’s ability to achieve goals in a wide range of environments."
[[Legg & Hutter (2007)]](https://ar5iv.labs.arxiv.org/html/0712.3329#S2.SS6)
Legg & Hutter define intelligence mathematically in their paper but the vague intuition works well for the Course.
Steve Wozniak has the clever/cute
[Coffee Test](https://en.wikipedia.org/wiki/Artificial_general_intelligence#Tests_for_testing_human-level_AGI)
to determine whether a system possesses general intelligence. 

> A machine is required to enter an average American home and figure out how to make coffee: find the coffee machine, find the coffee, add water, find a mug, and brew the coffee by pushing the proper buttons.

Although the Course doesn't officially cover the various types of intelligent agents, I'd like to do so below for the most popular kinds:
- **Transformative AI [TAI]**: An AI that brings about a dramatically different future (roughly comparable but probably more significant than the agricultural or industrial revolution). [[OpenPhil]](https://www.openphilanthropy.org/research/some-background-on-our-views-regarding-advanced-artificial-intelligence/#:~:text=Roughly%20and%20conceptually%2C%20transformative%20AI,the%20agricultural%20or%20industrial%20revolution.)
- **Artificial General Intelligence [AGI]**: An AI that's broadly capable of most/all functions that an animal (traditionally a human) can do. We are still within the scale of what we can comprehend as intellectuals have created a rough intuitive scale of ants, bees, crows, & humans. We're quickly scaling up the ladder as artificial minds become more and more capable - see Galaxy timelines chart where mouse-brain-sized model is projected for 2023.
   - Fun fact: Orangutans, pigs, and octopi are among the smartest, less well-known animals (most think of chimps, dolphins, or mice first with a [longer list here](https://thehumaneleague.org/article/animal-intelligence))
- **Seed AI**: An AGI that recursively rewrites its own source code without human intervention. [[Yudkowsky (2007)]](http://intelligence.org/files/LOGI.pdf)
- **Superintelligent AI**: An agent that far surpasses the brightest human minds both individually and even what can be done collectively. If the Manhattan Project was the combination of the brightest minds, a superintelligent agent would view them as intellectually equal as we view ants (but probably even more inferior in this axis if my anthropological lens is true in the first place).
   - In my view, an AGI will very likely become a superintelligent agent. We'd need to bound the AGI or rethink how we design AI systems. Bostrom explores several boxing methods in his [book](https://en.wikipedia.org/wiki/Superintelligence:_Paths,_Dangers,_Strategies) that aren't all that promising and suggests of coming up with novel ways to ensure that a Seed AI has certain values "pre-loaded."

## Timelines

Although AIs struggle right now with generalizing, 
I believe our uniqueness & intellectual superiority will _largely_ fade by the end of this century.
This forecast of "TAI is ~80% likely by the end of this century" (paraphrasing) comes mainly from the [2020 Bio-anchors paper](https://www.alignmentforum.org/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines) by Ajeya Cotra.
Holden Karnofsky later [summarizes where the "Experts" stood in 2021,](https://www.cold-takes.com/where-ai-forecasting-stands-today/)
and he concludes a ~2/3 chance by the end of this century. 
Cotra later [updated](https://www.alignmentforum.org/posts/AfH2oPHCApdKicM4m/two-year-update-on-my-personal-ai-timelines)
her forecast in 2022 with the median likelihood to be ~2040 now vs. ~2050 previously.
By induction, I can assume that she also increased her ~80% forecast of TAI by the end of this century as well. 
It is worth noting that these forecasts are to bound our expectations vs. seeing them as precise figures.
[Metaculus](https://www.metaculus.com/questions/5121/date-of-artificial-general-intelligence/) has its median forecast for AGI around 2035 during this writing.

<img src="/assets/2020-cotra-forecast.png" alt="Cotra2020FC" width="1024" class="center"/>

_Chart from [Bio-Anchors by Cotra from Cold Takes](https://www.cold-takes.com/forecasting-transformative-ai-the-biological-anchors-method-in-a-nutshell/)_

Given these timelines, I hope (and with modest confidence believe) we're in the [slow takeoff scenario](https://sideways-view.com/2018/02/24/takeoff-speeds/)
where we'll see continuous acceleration of technological progress. Practically speaking, I don't think 
there's much value in considering a fast takeoff scenario as we'd be unable to react to a superintelligent agent.

The bulleted list of the types of intelligence has a feeling of increasing levels of complexity or impressiveness. 
A lighter version is explored in several candid/hopeful short stories in **AI 2041** by Kai-Fu Lee. 
He describes _realistic AI,_ or "technologies that either already exist 
or can be reasonably expected to mature within the next twenty years."
Lee & other leaders in AI plausibly seem skeptical of TAI happening this century. 
I think the best resource pushing back on this view is from
[All Possible Views About Humanity's Future Are Wild](https://www.cold-takes.com/all-possible-views-about-humanitys-future-are-wild/)
by Holden Karnofsky.
In this post Karnofsky explores this "conservative view" by steelmanning various timelines of 100 years to 100,000 years.
For galaxy-scale timelines this range would converge on the same pixel in the visual below.
Granted the level of urgency would (thankfully) lift from our collective ~10 billion shoulders alive this century.
However, we'd still be among a tiny group of people placed in an important time period.
With 125 quadrillion (10<sup>15</sup>) [possible future persons on Earth](https://ourworldindata.org/longtermism#our-potential-future),
we're in the first ~100 billion people so far (or among the first 0.0001% people to ever exist on this planet).
In other posts Karnofsky expands on the challenges within AI safety & that many problems remain unsolved.
The rest of the Course focuses on the various problems & issues that emerge. <sup>[1](./AGI-Safety-Summary-Part-1#footnotes)</sup>

<img src="/assets/2021-karnofsky-cosmic-endowment.png" alt="Karnofsky2021Cosmic" width="1012"/>

_[Image from Cold Takes](https://www.cold-takes.com/forecasting-transformative-ai-the-biological-anchors-method-in-a-nutshell/)_

Additionally, I will outline another approach to understanding AI timelines and the main players in the space.
EFF used to [track various narrow AI/ML metrics](https://www.eff.org/ai/metrics)
with the last entries from Feb-2019, ending with GPT2. 
The main story then (and still today) is that progress is happening rapidly. 
Riedel & Deibel put together a [bibliographic database](https://www.lesswrong.com/posts/4DegbDJJiMX2b3EKm/tai-safety-bibliographic-database)
for the 16 major institutions (excluding academia) tracking the output of AI safety papers.
Relatedly, ~25% of deep learning papers come from the
[Fortune Global 500 (Tech)](https://en.wikipedia.org/wiki/List_of_Fortune_500_computer_software_and_information_companies)
companies.

<img src="/assets/2020-Compute-Inequality.png" alt="AIGini" width="1024" class="center"/>

_[Figure from this paper](https://arxiv.org/pdf/2010.15581.pdf)_

And ~40% of deep learning research comes from the Top 50 Universities.
This is consistent with Tim Dettmers’ broad statement about research in his 
[blog post:](https://timdettmers.com/2022/03/13/how-to-choose-your-grad-school/#School_Name_and_Resources) 
“0.0006% of people publish 41% of papers in research journals.”
I'm noting the inequalities in research as I imagine these will maintain for the foreseeable future. Week 7 _might_ cover this trade-off between "small research community collaborating efficiently prone to ivory tower type biases" and "large research community slowly integrating various perspectives."

The Course defines the recently created term "foundation models."
A foundation model is a model trained on broad data that can be fine-tuned to a range of more specific tasks.
The scale & scope of foundation models are what makes it unique. 
AI progress traditionally has 3 inputs: software, hardware, and data. 
To me, the term foundation model is emphasizing the leveraging of Moore's Law (hardware acceleration via improved computation costs)
that's able to intake mountains of data ([Sutton's scaling law](http://www.incompleteideas.net/IncIdeas/BitterLesson.html))
in larger, generalized methods via transformers (new software from a 2017 paper).
Bringing this all together, it seems like foundation models might be the catalyst in which we see TAI.

# Week 2: Reward misspecification and instrumental convergence 🏅

We refined our formal definition of intelligence & have some high-level intuition of progress & capabilities for AI.
Why put safety into "AGI Safety" at all? This how I was introduced to the Alignment Problem:

> 1. **Orthogonality Thesis**: Intelligence and final goals can be two different axes within an AGI. Therefore, the space of possibilities includes "Superintelligence, Misaligned with Human Goals." [Bostrom]
> 2. An AGI being misaligned to human values seems more likely than to be aligned. This is because by-and-large the AGI will seek power (almost always an **instrumental goal**) to accomplish its terminal or final goal. [Omohundro]
> 3. Even if the above two are solved, it is still possible for an AGI to create a terrible outcome that results from the **value loading problem.**
>    - Using the example goal of "cure cancer" to an AGI: the AGI _could_ solve for this by giving everyone a pill where they die at the age of 40. The AGI found that cancer is much more common in old age and solved the goal given but is not aligned with human values.

_From my ["Why AGI?"](./Why-AGI#beliefs--arguments) post_

[MIRI](https://intelligence.org/2013/05/05/five-theses-two-lemmas-and-a-couple-of-strategic-implications/) 
also has these points and more in their major concerns for alignment. 

The Course begins to break down these "what could go wrong" theses focusing first on reward misspecification.
**Reward misspecifications** occur because real-world tasks have numerous, often conflicting desiderata.
**Reward hacking** (a subset of reward misspecification) is where RL agents exploit gaps in misspecified reward functions.
[[Pan (2022)]](https://ar5iv.labs.arxiv.org/html/2201.03544) 
The other type of reward misspecification is from humans not designing the correct reward function in the first place
(e.g. [CoastRunners example](https://openai.com/research/faulty-reward-functions)).
**Specification gaming** is a behavior that satisfies the literal specification of an objective
without achieving the intended outcome.
[[Deepmind (2020)]](https://www.deepmind.com/blog/specification-gaming-the-flip-side-of-ai-ingenuity)
Point 3 above is one hypothetical example of many.<sup>[2](./AGI-Safety-Summary-Part-1#footnotes)</sup>

Instead of explicitly outlining our criteria directly into a reward function, 
researchers have implemented a couple methods of allowing an AI to learn from humans.

1. **Reinforcement Learning from Human Feedback [RLHF]:** A "human in the loop" process where a human judge ranks two outputs with one being better than the other. Then, feed that information back into the model and iterate. 
2. **Inverse Reinforcement Learning:** Allows the reward function to be learned (or create a black-box model of the reward function) purely from observations.

If you're not convinced & short on time, I think the most accessible resource for the AGI alignment problem is in
[What failure looks like](https://www.alignmentforum.org/posts/HBxe6wdjxK239zajf/what-failure-looks-like)
by Paul Christiano, which I think could make for an interesting novel.

Is it an AI Catastrophe for AGI to give us the entire Milky Way but take over the rest of the universe? Upon first glance, it seems like missing out on our cosmic endowment isn’t ideal, but it’s better than going extinct.

# Week 3: Goal misgeneralization 🥅

- **Goal misgeneralization:** An instance of misgeneralisation in which a system’s capabilities generalise but its goal does not generalise as desired. [Deepmind (2022)](https://deepmindsafetyresearch.medium.com/goal-misgeneralisation-why-correct-specifications-arent-enough-for-correct-goals-cf96ebc60924)<sup>[3](./AGI-Safety-Summary-Part-1#footnotes)</sup>
- **Situational awareness:** At some point, an AI agent becomes knowledgeable enough to understand that it's a deep learning model being trained to accomplish some goal. This kind of knowledge "is likely helpful for getting good performance on complex real-world tasks." [[Cotra (2021)]](https://www.cold-takes.com/why-ai-alignment-could-be-hard-with-modern-deep-learning/)
- **Outer alignment:** The human takes their meta-objective and codes this into the base objective function with an AI agent.
- **Inner alignment:** Further inside the AI agent, the system has a mesa-objective encoded via its deep learning architecture.
   - Evolution Analogy: Evolution's goal is for us to produce as many offspring as possible. This is the base objective. Yet, humans puruse many goals that may or may not relate to Evolution's goals (say being happy for its own sake). We may have inner alignment with evolution. Yet, it's possible to be inner misaligned by being childfree. Evolution did its outer alignment job and created a person. 
   - _It's also possible for evolution to have outer misalignment in the case of dodo bird where it was able to produce offspring yet winning the (possibly the first?) [Darwin Award](https://en.wikipedia.org/wiki/Darwin_Awards) as it was unfit for survival when sailors brought them to extinction._

Another problem that emerges within this category is being deceptively aligned.
While I generally try to avoid anthropomorphising AI, it is easier to imagine an AI that behaves well during training while _knowing_ it is in training. Then once deployed, it will pursue its real goals. Ideally, we want to avoid this kind of misalignment, and this remains an active realm of research. Cotra creates an analogy where you've inherited a substantial amount of wealth as an 8-year-old (strikingly similar to Harry Potter) yet without a trusted adult. Therefore, the goal is then to set up a process/test to find the "Saints" knowing the other two types exist. Cotra outlines 3 types of models/agents we're likely to encounter using the deep learning paradigm.
- Saints: genuinely want to help you.
- Sycophants: want your approval, regardless of long-term consequences
- Schemers: want your wealth to pursue their own agendas.

We have already seen [simpler forms of deception.](https://openai.com/research/learning-from-human-preferences#challenges) In this example, the goal was for the digital robot arm to grab the ball. Yet, it found the greedy solution was to place itself between the ball and camera making it appear as if it accomplished the goal. While this is a toy example with a concrete goal, how would we go about solving real-world problems that have fuzzy goals?

# Week 4: Task decomposition for scalable oversight 👀

- **Scalable Oversight:** The problem of supervising systems that potentially outperform us on most skills relevant to the task at hand.
- **Task decomposition:** 
- **Iterated amplification:**

<img src="/assets/2021-christiano-alignment-map.jpeg" alt="ChristianoMap" width="1024" class="center"/>

# Week 5: Adversarial techniques for scalable oversight 👾 

# Week 6: Interpretability 🔍

# Week 7: Agent Foundations & Governance 🏛️
_My cohort chose Agent Foundations while I preferred the default choice of Governance/Strategy._

## Agent Foundations

## Governance 
- [When AGI is a 'Manhattan Project' away](https://arxiv.org/ftp/arxiv/papers/2008/2008.04701.pdf)
- [Anthropics LLM Surprise](https://arxiv.org/abs/2202.07785)
- [Holden's AI Strategy set of questions](https://forum.effectivealtruism.org/posts/zGiD94SHwQ9MwPyfW/#Questions_about_AI_strategy__more_)
- [Stanford AI Index](https://aiindex.stanford.edu/report/)
- [Why TAI is hard](https://thegradient.pub/why-transformative-artificial-intelligence-is-really-really-hard-to-achieve/)
- [Compute Monitoring](https://ar5iv.labs.arxiv.org/html/2303.11341)

# Footnotes 🦿
1. I'm borrowing the mathematical definition of "problem" where a solution _may_ exist. [[Wikipedia]](https://en.wikipedia.org/wiki/Mathematical_problem) Some problems don't have a solution (e.g. free will, absolute moral truths etc.). I think what is usually meant is "issue" where there _is_ an existing solution, whether it's known or unknown.
2. The researchers at Deepmind made a
[combined list](http://tinyurl.com/specification-gaming)
of specification gaming examples from AI research if that's of interest.
3. The researchers at Deepmind made a different
[combined list](http://tinyurl.com/goal-misgeneralisation)
of goal misgeneralization examples from AI research if that's of interest.


# Links to Materials [~7 hours] 🔗

_I made a [Spotify Playlist](https://open.spotify.com/playlist/4RV5q7Z49XZflV38NoahF5?si=2567ed53d3944784) for the 
2022 iteration of the Course with **some** of the readings that should be viewed as supplemental and not as a substitution.
Lastly, I add in optional readings that I personally view as important enough to be included here & would recommend._ 

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
- [[Optional] The Bitter Lesson (2019) by Rich Sutton](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
- [[Optional] AI and Efficiency (2020) by Danny Hernandez and Tom Brown](https://openai.com/research/ai-and-efficiency)
- [[Optional] AI and Compute (2022) by Andrew Lohn and Micah Musser](https://cset.georgetown.edu/wp-content/uploads/AI-and-Compute-How-Much-Longer-Can-Computing-Power-Drive-Artificial-Intelligence-Progress.pdf)

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

---

## Materials for Week 4: Task decomposition for scalable oversight [~110 minutes]
- [[Video] AI Alignment Landscape (2020) by Paul Christiano](https://forum.effectivealtruism.org/posts/63stBTw3WAW6k45dY/paul-christiano-current-work-in-ai-alignment)
- [Measuring Progress on Scalable Oversight for Large Language Models (2022) by Samuel Bowman](https://ar5iv.labs.arxiv.org/html/2211.03540)
- [Learning Complex Goals with Iterated Amplification (2018) by Paul Christiano and Dario Amodei](https://openai.com/blog/amplifying-ai-training/)
- [Supervising strong learners by amplifying weak experts (2018) by Paul Christiano, Dario Amodei and Buck Shlegeris](https://ar5iv.labs.arxiv.org/html/1810.08575)
- [Summarizing Books with Human Feedback (2021) by Jeffrey Wu, Ryan Lowe and Jan Leike](https://openai.com/research/summarizing-books)
- [Language Models Perform Reasoning via Chain of Thought (2022) by Jason Wei, Denny Zhou and Google](https://ai.googleblog.com/2022/05/language-models-perform-reasoning-via.html)
- [Least-to-Most Prompting Enables Complex Reasoning in Large Language Models (2022) by Denny Zhou et alia](https://ar5iv.labs.arxiv.org/html/2205.10625)

--- 

## Materials for Week 5: Adversarial techniques for scalable oversight [~90 minutes]
- [AI-written critiques help humans notice flaws: blog post (2022) by Jan Leike et alia](https://openai.com/research/critiques)
- [AI safety via debate (2018) by Geoffrey Irving, Paul Christiano and Dario Amodei](https://ar5iv.labs.arxiv.org/html/1805.00899)
- [Red-teaming language models with language models (2022) by Ethan Perez et alia](https://www.deepmind.com/blog/red-teaming-language-models-with-language-models)
- [[Advanced ML] Robust Feature-Level Adversaries are Interpretability Tools (2021) by Casper et alia](https://ar5iv.labs.arxiv.org/html/2110.03605)
- [High-stakes alignment via adversarial training blog posts (2022) by Daniel Ziegler et alia](https://www.alignmentforum.org/posts/A9tJFJY7DsGTFKKkh/high-stakes-alignment-via-adversarial-training-redwood)
- [Takeaways from our robust injury classifier project (2022) by Daniel Ziegler et alia](https://www.alignmentforum.org/posts/n3LAgnHg6ashQK3fF/takeaways-from-our-robust-injury-classifier-project-redwood)
- [[Optional] WebGPT (2021) by Jacob Hilton et alia](https://openai.com/research/webgpt)
- [[Optional] Debate update: Obfuscated arguments problem (2020) by "Beth Barnes" and Paul Christiano](https://www.alignmentforum.org/posts/PJLABqQ962hZEqhdB/debate-update-obfuscated-arguments-problem)
- [[Optional] Training robust corrigibility (2019) by Paul Christiano](https://ai-alignment.com/training-robust-corrigibility-ce0e0a3b9b4d)

--- 

## Materials for Week 6: Interpretability [~100 minutes]
- [Feature Visualization (2017) by Chris Olah et alia](https://distill.pub/2017/feature-visualization/)
- [Zoom In: An Introduction to Circuits (2020) by Chris Olah et alia](https://distill.pub/2020/circuits/zoom-in/)
- [[Advanced ML] Toy Models of Superposition (2022) by Nelson Elhage et alia](https://transformer-circuits.pub/2022/toy_model/index.html)
- [Understanding intermediate layers using linear classifier probes (2016) by Guillaume Alain and Yoshua Bengio](https://ar5iv.labs.arxiv.org/html/1610.01644)
- [[Advanced ML] Discovering Latent Knowledge in Language Models Without Supervision (2022) by Collin Burns](https://ar5iv.labs.arxiv.org/html/2212.03827)
- [Acquisition of Chess Knowledge in AlphaZero (2021) by Thomas McGrath et alia](https://ar5iv.labs.arxiv.org/html/2111.09259)
- [Locating and Editing Factual Associations in GPT (2022) by Kevin Meng et alia](https://rome.baulab.info/)
- [[Advanced ML & Optional] Eliciting latent knowledge (2021) by Paul Christiano et alia](https://docs.google.com/document/d/1WwsnJQstPq91_Yh-Ch2XRL8H_EpsnjrC1dwZXR37PC8/edit)
- [[My Addition] Chris Olah Interview on the 80k Podcast](https://80000hours.org/podcast/episodes/chris-olah-interpretability-research/)

--- 

## Materials for Week 7 - Default: Governance [~80 minutes]
- [[Video] AI Strategy, Policy, and Governance (2019) by Allan Dafoe](https://www.youtube.com/watch?v=2IpJ8TIKKtI)
- [AI Governance: Opportunity and Theory of Impact (2020) by Allan Dafoe](https://www.governance.ai/research-paper/ai-governance-opportunity-and-theory-of-impact)
- [The AI deployment problem (2022) by Holden Karnofsky](https://www.cold-takes.com/racing-through-a-minefield-the-ai-deployment-problem/)
- [Why and How Governments Should Monitor AI Development (2021) by Jess Whittlestone and Jack Clarke](https://ar5iv.labs.arxiv.org/html/2108.12427)
- [Transformative AI and Compute (2021) by Lennart Heim](https://www.alignmentforum.org/s/bJi3hd8E8qjBeHz9Z)
- [Information security considerations for AI and the long term future (2022) by Jeffrey Ladish and Lennart Heim](https://forum.effectivealtruism.org/posts/WqQDCCLWbYfFRwubf/information-security-considerations-for-ai-and-the-long-term)
- [[Optional] Sharing Powerful AI Models (2022) by Toby Shevlane](https://www.governance.ai/post/sharing-powerful-ai-models)
- [[Optional] AI Governance: A research agenda (2018) by Allan Dafoe](https://www.fhi.ox.ac.uk/wp-content/uploads/GovAI-Agenda.pdf)
- [[Optional] Some AI governance research ideas (2021) by Markus Anderljung and Alexis Carlier](https://docs.google.com/document/d/13LJhP3ksrcEBKxYFG5GkJaC2UoxHKUYAHCRdRlpePEc/edit)
- [[Optional] The Semiconductor Supply Chain (2021) by Saif M. Khan](https://cset.georgetown.edu/publication/the-semiconductor-supply-chain/)
- [[Optional] The Global AI talent tracker (2020) by Macro Polo](https://macropolo.org/digital-projects/the-global-ai-talent-tracker/)
- [[My Addition] Could Advanced AI Drive Explosive Economic Growth (2021) by Tom Davidson](https://www.openphilanthropy.org/research/could-advanced-ai-drive-explosive-economic-growth/)
- [GPTs are GPTs by Tyna Eloundou et alia](https://arxiv.org/pdf/2303.10130.pdf)
- [Sparks of AGI in GPT4 by Sebastien Bubeck et alia](https://arxiv.org/pdf/2303.12712.pdf)

--- 

## Materials for Week 7 - Alternative: Agent Foundations [~100 minutes]
- [What is AIXI? (2020) by Marcus Hutter](https://www.youtube.com/watch?v=g4M7stjzR1I)
- [Embedded Agents: Part 1 (2018) by Scott Garrabrant and Demski](https://intelligence.org/2018/10/29/embedded-agents/)
- [Logical decision theory (2017) by Eliezer Yudkowsky](https://arbital.com/p/logical_dt/?l=5d6)
- [Logical Induction: Blog post (2016) by Nate Soares](https://intelligence.org/2016/09/12/new-paper-logical-induction/)
- [Progress on Causal Influence diagrams: blog post (2021) by Tom Everitt et alia](https://www.alignmentforum.org/posts/Cd7Hw492RqooYgQAS/progress-on-causal-influence-diagrams)
- [Avoiding Side Effects By Considering Future Tasks (2020) by Victoria Krakovna](https://arxiv.org/abs/2010.07877)
- [Cooperation, Conflict and Transformative AI (2019) by Jesse Clifton](https://www.alignmentforum.org/s/p947tK8CoBbdpPtyK/p/KMocAf9jnAKc2jXri)

