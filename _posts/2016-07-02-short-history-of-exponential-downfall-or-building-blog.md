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

<cite>&mdash; Umberto Eco, Focault's Pendulum</cite>

Or, to make myself clear, for an perfectly beautiful, enlightening pattern for
building a website, but it turns out to be kind of decision problem that I simply
can't compute. It's like a ordinary differential equation: in order to solve this problem,
you look at it until the solution occurs to you.[^1]

Reason for this *downfall* may lie in my lack of virtue (defined in Confucian sense).
Superficial treatment long-term planning and impatience caused many cogs of the
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
(yes, that's think we will talk about) and $$ a $$ is our assigned task. Let's say
that we want to describe our productivity in range of $$ 0 \leq P_a < 1 $$. Now, let's
make it dependant on $$ t $$ which describes the time. Now let's transform $$ P_a $$ into
a formal function $$ P_a: [0,1] \to \mathrm R $$. It won't be in any way precise, but it
will describe the concept:

$$
  P_a(t) = \left| \tfrac{3}{4} \pi^{-t} \right|
$$

As we can see up here, over the time, our productivity falls. At the begining we're not
using it all, and we're approaching the lower limit of it. If we translate the $$ a $$ task to
the task of writing code, it may seem only natural, because of the growing complexity, we may
be going forward to the state at which we have all planed features and all we make are fixes.
The limit of $$ t $$ is $$ 1 $$, or $$ 100\% $$, and it's a state at which the task is
finished.

What I don't like about this curve is that, it's discouraging. There is certain excitement
in *developement*[^6], and slowing down with this evolutionary process deprives of spirit.
Because the first path I have choosen was leading to this stagnation, I was looking for another
way, to make this curve more constant, containing minor fluctuations.

In rage, after falling into exponential downfall I've cleaned up the project, and started
working on it all over again. This time I decided to change pattern of workflow to have
control over the behaviour of this beast. I used the Bootstrap[^7] to scale down potential overall
time until the reaching the limit of $$ t $$. Once again I ended up with similar directory
structure and general project structure, divided into sections, and decided to move
to the next section before polishing previous if I was losing speed (observed in lower code
frequency on [github](http://github.com/)).

Now, we need to add up our functions to create the series of $$ P_a $$ and this will be
expressed by the following summation:

$$
  \displaystyle\sum_{i=1}^{n} P_n, \quad P_n(t_n) = \left| \tfrac{3}{4} \pi^{-t+(i-1)} \right|
$$

As you probably noticed, there is $$ n $$ subscript in our time variable. That's because
we need to expand domain of our function. Now it's $$ \{t_n \mid t \in \langle n-1, n \rangle, n \in \mathrm N\} $$

[^1]: Paraphrase of sentence from [George Pólya](https://pl.wikipedia.org/wiki/George_P%C3%B3lya) (1887-1985): *How to Solve It: A New Aspect of Mathematical Method* Princeton University Press, 1945
[^2]: Automation tool using JS and node.js, with large amount of plugins.
[^3]: Blog-aware static site generator.
[^4]: Template language for HTML.
[^5]: An extension of CSS that adds power and elegance to the basic language.
[^6]: [Defined as](http://www.thefreedictionary.com/development): *A significant event, occurrence, or change*
[^7]: Intuitive mobile first front-end framework which provides column layout with media queries.
