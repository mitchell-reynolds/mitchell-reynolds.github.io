*This post was written by Mark Xu based on interviews with Carl Shulman. It was paid for by Open Philanthropy but is not representative of their views.*

Summary
=======

*   The absence of evidence for extraterrestrial life suggests the existence of a Great Filter, a set of factors that in combination drive the probability of a given star producing expansionist interstellar civilization very low.
*   The self-indication assumption (SIA) says that you should think it more probable that you exist in worlds where there are more observers faced with your exact observations.
*   Several SIA Doomsday Arguments note that there can be more naturally developed observers on primitive planets if the Great Filter lies after us, e.g. civilizations like ours are incapable of space travel, self-destruct, or are suppressed by hidden aliens; thus such arguments claim SIA gives overwhelming reason to expect a civilization like ours to fail to expand.
*   However, these so-called SIA Doomsday Arguments don’t take into account the possibility of mature civilizations simulating previous ones.
    *   SIA overwhelmingly favors the hypothesis of simulations because it allows far more observers in our apparent position.
    *   The number of such simulations is maximized when colonization is frequent enough for a large share of all resources to be colonized, but is largely indifferent about precise frequencies given that; so SIA does not suggest that unsimulated civilizations that look like Earth face a late Great Filter.

Note that we are not endorsing the underlying SIA decision making framework here, only discussing whether certain conclusions follow it. In dealing with such anthropic problems we would prefer approaches closer to Armstrong’s [Anthropic decision theory](https://arxiv.org/abs/1110.6437), which we think is better for avoiding certain sorts of self-destructive anthropic confusions.

Introduction
============

The [search for extraterrestrial intelligence](https://en.wikipedia.org/wiki/Search_for_extraterrestrial_intelligence) has not yet yielded fruit. [Hanson (1998)](https://mason.gmu.edu/~rhanson/greatfilter.html) argues that this implies the probability of life evolving on a planet and becoming visible must be extremely low, a so-called Great Filter. Such a filter could be located in many possible difficulties: abiogenesis, intelligent life, interstellar colonization, etc. Humanity’s future prospects may depend on whether the difficulties have already passed or lie ahead. Thus we are left with a troubling question: how far along the filter are we?

[Sandberg et al. (2018)](https://arxiv.org/pdf/1806.02404.pdf) observe that current scientific uncertainty is compatible with a high chance that we are alone in the universe. For example, Sandberg et al. suggest over 200 orders of magnitude of uncertainty over the frequency of abiogenesis. Since there is substantial prior probability on early Great Filters, the lack of visible extraterrestrial life can’t provide a very large likelihood ratio regarding late filters.  

However, on the Self-Indication Assumption (SIA) the fact that we find ourselves to exist should provide overwhelming reason to reject theories of very large early filters, and purportedly favor late filters.

We will discuss how the Great Filter interacts with SIA. We will first introduce the assumption and then present [Grace (2010)](https://katjagrace.files.wordpress.com/2021/05/anthropic_reasoning_in_the_great_filter_final_thesis.pdf) and [Ord and Olsen (2020)](https://arxiv.org/pdf/2106.13348.pdf)’s arguments that SIA implies the Great Filter is ahead, which we will call the “SIA Doomsday Argument”. We will then argue that Bostrom’s [simulation argument](https://www.simulation-argument.com/) reverses the conclusion of the SIA Doomsday Argument.

Self-Indication Assumption
==========================

The self-indication assumption:

> (SIA): Observers should reason as if they were a random sample from all possible observers. Observers should reason as if they have a probability of being in a world proportional with the number of observers it contains. Worlds where a higher *number* of observers are “like you” are more probable.

To illustrate applications of SIA, we will discuss two examples due to [John Leslie](https://www.routledge.com/The-End-of-the-World-The-Science-and-Ethics-of-Human-Extinction/Leslie/p/book/9780415184472) and [Nick Bostrom](https://www.anthropic-principle.com/preprints/mys/mysteries.pdf).

> God’s Coin Toss: Suppose that God tosses a fair coin. If it comes up heads, he creates ten people, each in their own room. If tails, he creates one thousand people, each in their own room. The rooms are numbered 1-10 or 1-1000. The people cannot see or communicate with the other rooms. Suppose that you know all this, and you discover that you are in one of the first ten rooms. How should you reason that the coin fell?

To answer this question using SIA, one must take the prior probabilities of each world existing, then weight them by the number of people that are in the first ten rooms. Since both worlds have ten people who are in the first ten rooms and the worlds were equally probable, SIA advises that you think the coin was equally likely to have fallen heads or tails.

> The Presumptuous Philosopher: It is the year 2100 and physicists have narrowed down the search for a theory of everything to only two remaining plausible candidate theories: T1 and T2 (using considerations from super-duper symmetry). According to T1 the world is very, very big but finite and there are a total of a trillion trillion observers in the cosmos. According to T2, the world is very, very, very big but finite and there are a trillion trillion trillion observers. The super-duper symmetry considerations are indifferent between these two theories. Physicists are preparing a simple experiment that will falsify one of the theories. Enter the presumptuous philosopher: “Hey guys, it is completely unnecessary for you to do the experiment, because I can already show you that T2 is about a trillion times more likely to be true than T1!” 

Since super-duper symmetry considerations are indifferent between T1 and T2, they are equally probable. However, T2 implies a trillion times as many observers as T1. Under SIA, an observer is thus a trillion times more likely to find themselves in a world where T2 is true than a world in which T1 is true. [^FNIC]

[^FNIC]: Also see [Radford Neal](https://arxiv.org/abs/math/0608592) on getting similar conclusions in finite worlds with no duplicate observers. Note that this approach is self-undermining in that it requires no duplicates to drive reasoning, but also predicts overwhelmingly that many duplicates will exist.

SIA Doomsday Argument
=====================

We will simplify discussion by supposing that there are only two stages of the Great Filter: getting to where humanity is now, and getting from now to an intergalactic civilization. Let $$p_{develops}$$ be the probability that any given star develops life at humanity’s current level of technological maturity. Let $$p_{expands}$$ be the probability that a civilization with Earth’s current level of technology expands into an intergalactic civilization. The absence of evidence for other intergalactic civilizations suggests that $$p_{develops} * p_{expands} << 1$$. 

[Grace (2010)](https://katjagrace.files.wordpress.com/2021/05/anthropic_reasoning_in_the_great_filter_final_thesis.pdf) explains the SIA Doomsday Argument: 

> According to SIA, our future is far more likely to contain large filters than we naively think (or hope). ... \[T\]he Fermi Paradox implies that small filters in our past require large filters in our future, and under SIA smaller filters in our past get a boost in probability... \[S\]maller filters in our past mean more solar systems reach our stage, so there are more observers at our stage, making us more likely to exist. Since we do exist, SIA favors the hypothesis which predicted that with higher credence.
>
> The shift under SIA can be very large. Even if we thought the probability of half of the filter being in our future was one in a billion, and all the rest of our distribution was on future filters with a total of one order of magnitude or less strength, after using SIA we would be fairly confident in the large future filter.

[Olson and Ord (2021)](https://arxiv.org/pdf/2106.13348.pdf) illustrate the results of a similar argument:

> \[S\]uppose you attended two lectures, back-to-back, by two equally convincing experts — the first discussing insurmountable difficulties of relativistic space flight, and the second discussing the resources available to a technologically mature civilization.
>
> Emerging from the lecture hall, you find yourself conflicted, splitting your credence equally between two views of the universe. One in which the maximum practical expansion speed of an ambitious civilization is about $$v = .1$$ \[times the speed of light\], and in the other view somewhere around $$v = .9$$ \[times the speed of light\]. Then, invoking the SIA together with the possibility of expanding civilizations implies you should be 99.9% convinced of the low-speed scenario (because it leaves room for $$\approx 1,000$$ times as many human-stage civilizations to have originated at the present time).

In our two step filter model, the SIA Doomsday Argument is the observation that SIA favors higher *numbers* of intelligent observers at our technological stage, which provides pressure for $$p_{develops}$$ to be as large as possible. However, the lack of evidence for extraterrestrial life puts pressure on $$p_{develops} * p_{expands}$$ to be very small, suggesting that $$p_{expands}$$ is small.

SIA places linear pressure on $$p_{develops}$$ to be large (and thus also on $$p_{expands}$$ to be small); at each stage, SIA assigns ten times higher probability to worlds in which $$p_{develops}$$ is ten times as large. If, for example, one requires that $$p_{expands} * p_{develops} \approx 10^{-10}$$ and one’s uncertainty over $$p_{develops}$$ is log-uniform from $$10^{-10}$$ to $$10^{0}$$, SIA would exponentially favor $$p_{develops}$$ falling into higher orders of magnitude, concentrating almost all probability mass on relatively high values of $$p_{develops}$$ (and thus on low values of $$p_{expands}$$). Here is the update illustrated graphically: ([https://www.desmos.com/calculator/8baeummm7y](https://www.desmos.com/calculator/8baeummm7y)) 

![](https://lh4.googleusercontent.com/Dwt8ZHU3O3Q1XR2Pls9fwImoE4QHM6g14EmqZsmX5Grdq_fTBGwni-F74UepRMitQlujLRSWCrUTqQ3yAGHTyImJaW_6n4XcDGTuaTLM4ycqt9MNy30F0w2a7zIzeAhqh_X2kzjp=s0)

The above model is slightly simplified. In reality, very high values of $$p_{develops}$$ imply there are many intelligent civilizations close to our own, contradicting observation. SIA pushes $$p_{develops}$$ as high as possible without making it extremely unlikely that we observe an empty galaxy.

The implication in this model seems to be that under SIA we should expect that the bulk of the filter is still ahead. Given that it seems like object-level considerations about the probability of existential risk and the technological feasibility of intergalactic colonization do not warrant that expectation, this would mean we were adopting surprising conclusions about the physical world based on this presumptuous philosophical argument.

However, a hidden premise in these arguments is that observers only seem to find themselves at our stage of technological maturity in between abiogenesis and intergalactic colonization. The possibility of computer simulations plausibly invalidates this assumption.

The Simulation Argument
=======================

Under certain plausible assumptions, intergalactic civilizations might be able to create computer simulations containing many orders of magnitude more observers than natural primitive civilizations could support. In particular, Bostrom’s [Simulation Argument](https://www.simulation-argument.com/)  argues that at least one of the following is true:

1.  The human species is very likely to go extinct before reaching a “posthuman” stage.
2.  Any posthuman civilization is extremely unlikely to run a significant number of simulations of their evolutionary history (or sampling of other possible histories/civilizations/planets).
3.  We are almost certainly living in a computer simulation.

Since the various disjuncts in the Simulation Argument have implications on the expected number of observers that are “like you”, SIA favors some over others. If humanity develops into an intergalactic civilization and devotes a small fraction of resources (an immense amount by today’s standards) to producing simulations with observations like ours, there will be many orders of magnitude more observers in our apparent situations. Since SIA favors worlds where the absolute number of such observers is high, SIA vastly favors such a world. [^shulmanbostrom]

[^shulmanbostrom]: Shulman and Bostrom make a similar argument in section 4 of [How Hard is Artificial Intelligence?](https://www.nickbostrom.com/aievolution.pdf)

More specifically, if (1) or (2) were true, there would be no computer simulations of observers in our apparent situations. However, since such simulations possibly vastly outnumber the possible quantity of biological humans, (1) and (2) are both extremely heavily penalized by SIA. Indeed, even if you suspect that simulations will be difficult, will not be conscious, etc., if you were mistaken, then there would be trillions and trillions of observers. Since the SIA Doomsday Argument already embraces Presumptuous Philosopher-style reasoning on the Great Filter, it is difficult to see why it would inconsistently abandon that practice with respect to the simulation argument.

Considering our two step filter model, we are interested in the values of $$p_{develops}$$ and $$p_{expands}$$ in non-simulated reality. A low value of $$p_{expands}$$ suggests that (1) is true, which is improbable under SIA. For example, suppose an intergalactic civilization would produce a trillion times more simulated observers in our apparent situations per galaxy than the SIA Doomsday scenario of frequent primitive civilizations that get filtered without colonization. Since there are currently around 10 billion such observers, SIA favors the expansion+simulation hypothesis vs SIA Doomsday by a trillion to one, other things equal.

In general, SIA puts pressure on $$p_{develops} * p_{expands}$$ to be high enough such that nearly all resources in bedrock reality can be used for simulations. Since [the speed of intergalactic colonization](https://www.fhi.ox.ac.uk/publications/armstrong-s-sandberg-a-2013-eternity-in-six-hours-intergalactic-spreading-of-intelligent-life-and-sharpening-the-fermi-paradox-acta-astronautica-89-1-13/) is fast relative to the amount of time it takes civilizations to mature, the $$p_{develops} * p_{expands}$$ needs to be close (on the log scale) to enough to produce one intergalactic civilization per [affectable region of the universe](https://arxiv.org/abs/2104.01191). However, the SIA Doomsday scenario, with much more frequent primitive civilizations that ~uniformly fail to colonize, decreases the amount of colonization, and is thus penalized by SIA.    

SIA therefore advises not that the Great Filter is ahead, but rather that we are in a simulation run by an intergalactic human civilization, without strong views on late filters for unsimulated reality.