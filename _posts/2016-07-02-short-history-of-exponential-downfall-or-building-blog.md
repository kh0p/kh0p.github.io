---
layout: post
title: Short history of exponential downfall, or&#58; building blog
tags: [blog, work, web]
img: short-history-of-exponential-downfall-or-building-blog.jpg
---

For lack of better word, my experience with *developing* was terrible. I was
looking for:

>that number which, however irrational to sublunar minds, through a
higher rationality binds the circumference and diameter of all possible circles.

<cite>&mdash; [Umberto Eco](https://pl.wikipedia.org/wiki/Umberto_Eco), Focault's Pendulum</cite>

Or, to make myself clear, for an perfectly beautiful, enlightening pattern for
building a website, but it turns out to be kind of decision problem that I simply
can't compute. It's like a ordinary differential equation: in order to solve this problem,
you look at it until the solution occurs to you.[^1]

Reason for this *downfall* may lie in my lack of virtue (defined in Confucian sense).
Superficial treatment of long-term planning and impatience caused many cogs of the
machine to malfunction - and that's the lesson, here at the very begining. We all
should read and devote ourselfs to the Confucian classics.

But let's get to the point: initialy I tought that I'll use Gulp[^2], Jekyll[^3], Jade[^4],
and Sass[^5] to build my website. Number of used components may imply an convoluted
system, but in fact, after putting the parts together, we get straightforward
environment to work with. The given tools are really simple and elegant. Yet, after
some time, having to think about Jekyll was distracting me, so I decided to make
separation to two developement phases: one concerning front, and the other back end of
the project.

Basically, I divided the project into *theme* and *main* part, where theme was a
collection of Jade files, Sass styling, and some JS plus jQuery all handled by Gulp to
rapidly make changes and see them putted to live. Gulp was watching files for changes and
if some occured, it refreshed the `localhost:3000`, and made them visible with transition
animations.

Afterwards, I strictly followed the *divide et impera* and divided Jade into partials, Sass
into tools, modules, sections and layouts, my JS into separate files for each task. It was
all good, until the pattern came up. I think it's well known thing to everyone. It was pattern
of *exponential downfall*.

We can define it in a abstract manner using $$ P_a $$ where $$ P $$ is our productivity
(yes, that's the thing we will talk about) and $$ a $$ is our assigned task. Let's say
that we want to describe our productivity in range of $$ 0 \leq P_a \leq 1 $$. Now, let's
make it dependant on $$ t $$ which describes the time. Now let's transform $$ P_a $$ into
a formal function $$ P_a: [0,1] \to \mathbb R $$. It won't be in any way precise, but it
will describe the concept:

$$
  P_a(t) = \left| \tfrac{3}{4} \pi^{-t} \right|
$$

As we can see up here, over the time, our productivity falls. At the begining we're not
using our full potential, and we're approaching the lower limit of the considered productivity.
If we translate the $$ a $$ task to the task of writing code, it may seem only natural,
because of the growing complexity, we may be going forward to the state at which we have all
planed features and all we make are fixes. The limit of $$ t $$ is $$ 1 $$, or $$ 100\% $$,
and it's a state at which the task is finished.

What I don't like about this curve is that, it's discouraging. There is certain excitement
in *developement*[^6], and slowing down with this evolutionary process deprives of spirit.
Because the first path I have choosen was leading to this stagnation, I was looking for another
way, to make this curve more constant, containing minor fluctuations.

In rage, after falling into exponential downfall I've cleaned up the project, and started
working on it all over again. This time I decided to change pattern of workflow to have
control over the behaviour of this beast. I used the Bootstrap[^7] to scale down potential overall
time until reaching the limit of $$ t $$. Once again I ended up with similar directory
structure and general project structure, divided into sections, and decided to move
to the next section before polishing previous if I was losing speed (observed in lower code
frequency on [github](http://github.com/)).

Now, we need to add up our functions to create the series of $$ P_a $$ and this will be
expressed by the following summation:

$$
  \displaystyle\sum_{i=1}^{n} P_n, \quad P_n(t_i) = \left| \tfrac{3}{4} \pi^{-t_i+\tfrac{-1+i}{2}} \right|
$$

As you probably noticed, there is $$ i $$ subscript in our time variable. That's because
we need to expand domain of our function. Now it's

$$
  \{\, t_i \mid t \in \langle \tfrac{n-1}{2}, \tfrac{n}{2} \rangle, i \in \mathrm N \,\}
$$

It's $$ \tfrac{1}{2} $$, because I wanted to get the length at which the $$ P_n $$ remains
on a relatively high level. When considering $$ P_n $$, we can see that
$$ \lim\limits_{t_i \to \varepsilon} P_n, \; \varepsilon = \tfrac{i}{2} $$
does not exist, but we can omit it for now. Also, the $$ \varepsilon $$ is a
*breaking point* of $$ P_n $$. I want to show, that average speed changes a bit
with this method, and it can be done by simple approximation with derivative.
This *average speed of change* in productivity will be described as:
$$ \omega = \frac{\Delta P}{\Delta t} = \frac{P(t_0+\Delta t)-P(t_0)}{\Delta t} $$,
but we need to use a summation to approximate each task first:

$$
  \omega = \displaystyle\sum_{i=1}^{n}\tfrac{\Delta P_n}{\Delta t_i} =
  \displaystyle\sum_{i=1}^{n}\tfrac{P_n(t_{i,0}+\Delta t_i)-P_n(t_{i,0})}{\Delta t_i}
$$

Each task after $$ P_1 $$, if we will scale down all $$ t_i $$ to the range of
$$ t \in \langle 0, 1 \rangle $$, at any given point in domain will be higher;
we could notice this by intuition, but I really wanted to give detailed reasoning
for vague concept that is conflicted with my praxeological point of view in some
way. It's just showing my *personal feelings* about tendencies in my work cycle.
Even if I have large distrust in models, and I tend to talk about this sort of
thing in terms of *human action* as presented by Ludwig von Mises[^8]
(*Tu ne cede malis, sed contra audentior ito*, I proudly inherit this motto),
but I like to express certain things in this way. It's *chaotic*, but in
a way that physics is chaotic. It is vast approximation, and it is not by any
means a deterministic prediction.

>Relativity eliminated the Newtonian illusion of absolute space and time; quantum
theory eliminated the Newtonian dream of a controllable measurement process;
and chaos eliminatesthe Laplacian fantasy of deterministic predictability.

<cite>&mdash; [Joseph Ford](https://en.wikipedia.org/wiki/Joseph_Ford_(physicist)), What is Chaos, That We Should Be Mindful of It?</cite>[^9]

End of divagation. Theory shows, that the proposed way should be more efficient.
It in fact is, as we can see by getting gradient of a line between points
$$ A_1 = (0, \tfrac{3}{4}) $$ and $$ B_1 = (1, \tfrac{3\sqrt{\pi}}{4\pi}) $$ that basically
are $$ (t_0, P_1(t_0)), \,(1, P_n(1)) $$ respectively, and putting it inside
a linear function $$ \delta(x) $$ that looks like this:

$$
  \delta_1(x) = -(\tfrac{3\pi-3\sqrt{\pi}}{4\pi})x + \tfrac{3}{4}
$$

and by doing the same thing for $$ A_2 = (0, \tfrac{3}{4}), \, B_2 = (1, \tfrac{3}{4\pi}) $$,
that are just $$ (t_0, P_a(t_0)), \,(1, P_a(1)) $$ in terms of $$ P_a $$ defined at the begining,
the new function is:

$$
  \delta_2(x) = -(\tfrac{3\pi-3}{4\pi})x + \tfrac{3}{4}
$$

And to end it all, because it's getting nonsensically obnoxious, we can summarize it by
the fact that:

$$
  \delta_1(x) < \delta_2(x), \: x \in \mathbb R-\{0\}
$$

In conclusion, this pattern that is similar to Scrum[^10] because of its *iterations*
that looks like something speeding up the process of development. That may
be an fact, but my implementation of it was scaled down in time, to really tiny units -
days. So that's one factor, but there is more. When I think of it, the concept of
iterations could work out perfectly, if not the interference of distraction, *value preference*
and *time preference*[^11], everything going back by full circle to praxeology.

This blog was a result of observation, that spending too much time on tweaking the
site was economicaly unprofitable, because I had other things to invest my
time in; the thought that there are this other things to do subconsciously was slowing
me down. So the story ended up right here, with Hyde theme for Jekyll,
my own hijacking of theme hijacked from Hyde (*Hydejack*), this post, and this
sentence.

*Sidenote*: Finding a way to make it an inverse function ($$ P_n^{-1} $$) that has
asymptote at $$ P_n(t_i) = 1 $$ would be clever.

[^1]: Paraphrase of sentence from [George Pólya](https://pl.wikipedia.org/wiki/George_P%C3%B3lya) (1887-1985): *How to Solve It: A New Aspect of Mathematical Method*, Princeton University Press, 1945
[^2]: Automation tool using JS and node.js, with large amount of plugins.
[^3]: Blog-aware static site generator.
[^4]: Template language for HTML.
[^5]: An extension of CSS that adds power and elegance to the basic language.
[^6]: [Defined as](http://www.thefreedictionary.com/development): *A significant event, occurrence, or change*
[^7]: Intuitive mobile first front-end framework which provides column layout with media queries.
[^8]: [Ludwig von Mises](https://en.wikipedia.org/wiki/Ludwig_von_Mises) (1881-1973), theoretical Austrian School economist; he is best known for his work on praxeology, a study of human choice and action: *Human Action: A Treatise on Economics*, Yale University Press
[^9]: [Joseph Ford](https://en.wikipedia.org/wiki/Joseph_Ford_(physicist)), *What is Chaos, That We Should Be Mindful of It?*, preprint, Georgia Institute of Technology, p. 12.
[^10]: It is an iterative and incremental agile software development framework for managing product development
[^11]: [Definition](http://www.investopedia.com/terms/t/time-preference-theory-of-interest.asp#ixzz4DT0eLzqb) of *Time-Preference Theory Of Interest*: A theory that examines the nature of consumerism, and the factors that influence consumers to delay current consumption or expenditures in anticipation of greater future returns. The rate of time preference itself can be quantified as the amount of money required to compensate the consumer for foregoing current consumption.
