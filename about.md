---
layout: page
title: About
---

{% comment %}
  This inserts the "about" photo and text from `_config.yml`.
  You can edit it there (jekyll needs restart!) or remove it and provide your own photo/text.
  Don't forget to add the `me` class to the photo, like this: `![alt](src){:.me}`.
{% endcomment %}

{% if site.author.photo %}
  ![{{ site.author.name }}]({{ site.author.photo }}){:.me}
{% endif %}

{{ site.author.about }}

## Reference

 - **Defalut sidebar image** [Thomas Cole](https://en.wikipedia.org/wiki/Thomas_Cole):
   *The Consummation of Empire*. Oil on canvas, 1836, 51 × 76 in. From five-part
   series of paintings called *The Course of Empire*.
 - **Blog** [John Singer Sargent](https://en.wikipedia.org/wiki/John_Singer_Sargent):
   *Carnation, Lily, Lily, Rose*. Oil on canvas,	1885, 68.5 × 60.5 in. The title
   comes from the refrain of a popular song *Ye Shepherds Tell Me* by
   [Joseph Mazzinghi](https://en.wikipedia.org/wiki/Joseph_Mazzinghi).
 - **Work** [Apollodorus of Damascus](https://en.wikipedia.org/wiki/Apollodorus_of_Damascus) (Greek: *Ἀπολλόδωρος*),
   bust from 130/140 AD. On display at Munich Glyptothek, *Saal XI: Saal der römischen Bildnisse*,
   No. 31.
