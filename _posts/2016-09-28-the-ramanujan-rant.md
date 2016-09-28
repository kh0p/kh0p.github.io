---
layout: post
title: The Ramanujan Rant, Part One
tags: [blog]
img: the-ramanujan-rant.png
---

If *Srinivasa Ramanujan* needs an introduction, this one may serve well:

> Back in early 1900s a class III math teacher pointed out that any number divided by itself gives one: divide three fruits among three people, each would get one. A Dark young boy with a strange confusion asked - “But is zero divided by zero also one? If no fruits are divided among no one will each still get one?” This confounding nature of the little boy after few years built The Great Mathematician Srinivasa Ramanujan FRS. He is the man who made marvelous contributions to number theory, infinite series, mathematical analysis, and continued fraction.

<cite>&mdash; [An Eminent Mathematical Genius: SRINIVASA RAMANUJAN](http://gyanpro.com/blog/an-eminent-mathematical-genius-srinivasa-ramanujan/)</cite>

He was a mathematician that inspired me by his approach; after reading about his work and himself, math started to appear to me like boundless thought process which you can describe in elegant way. I became familiar with it because it turned out to be more of a linguistic tool to communicate very abstract concepts. And maybe I could write down thousands of words that could praise him, but rather than that, I just wanted to gather some of his own thoughts and conclusions here. It will be more of a excercise in *LaTeX*[^1] *"nesting"*, because now, I want to explore some of his infinite roots and some other things.

$$
  3 = \sqrt{9} = \sqrt{1 + 8} = \sqrt{1 + 2\sqrt{16}} = \sqrt{1 + 2\sqrt{1 + 3\sqrt{25}}}
$$

As you can probably see, this one leads us to:

$$
  \sqrt{1 + 2\sqrt{1 + 3\sqrt{1 + 4\sqrt{1 + \cdots}}}}
$$

The interesting thing about this is that you can also do it to 4:

$$
  4 = \sqrt{16} = \sqrt{1 + 2\sqrt{\tfrac{225}{4}}} = \sqrt{1 + 2\sqrt{1 + 3\sqrt{\tfrac{48841}{144}}}} \cdots
$$

The other one that I would like to bring up and I really like is actually expression of $$ \phi $$; and yes, I really like it mainly because I always appreciate appearance of golden ratio. It's also very simple.  

$$
  \sqrt{1 + \sqrt{1 + \sqrt{1 + \cdots}}}
$$

To know from where it came from, just take a look:

$$
  x = \sqrt{1 + \sqrt{1 + \sqrt{1 + \cdots}}}
$$

$$
  x = \sqrt{1 + x}
$$

As I sidenote for myself, I need to point out problem with *KaTeX* - it looks like it doesn't support `\newline`, and it's very sad. But back to the math: afterwards it's a matter of solving simple quadratic equation. In the end, you should get $$ \tfrac{1 \pm \sqrt{5}}{2} $$, but we can safely assume that there is a plus sign:

$$
  \frac{1 + \sqrt{5}}{2} = \phi
$$

The last one I would like to cover is:

$$
  \frac{2}{3 - \tfrac{2}{3 - \tfrac{2}{3 - \tfrac{2}{3 - \ddots}}}}
$$

Which you can solve using same method as the one with golden ratio - getting quadratic equation and solving it. The solution is: $$ 1 \lor 2 $$.

Maybe it's very lazy of me, but that's it for now. I think that there's no need to push myself with writing extensive posts, when I can write smaller ones but hopefully regularly - it's three months after previous post. I pointed it out already but that was more of a *LaTeX* training than anything. I would like to write much more on the topic of Ramanujan's life, work and math, but you know - *time preference*. The credits for this post should go to the [Mathologer](https://www.youtube.com/watch?v=leFep9yt3JY), for gathering and explaining everything in simple way on his videos. 

[^1]: High-quality typesetting system; it includes features designed for the production of technical and scientific documentation.
