---
layout: page
title: About
permalink: /about/
published: true
---

<div class="page" markdown="1">

{% capture page_subtitle %}
<img
    class="me"
    alt="{{ author.name }}"
    src="{{ site.author.photo | relative_url }}"
    srcset="{{ site.author.photo2x | relative_url }} 2x"
/>
{% endcapture %}

{% include page/title.html title=page.title subtitle=page_subtitle %}
Hi,

My name is Kiet Tran. I am a junior studying mechanical engineering at the University of Minnesota, Twin Cities. I am hoping to build a career in mechatronics or aerospace industry in the near future. This blog shows the projects and activities that I was or currently is involved in.
</div>

{% capture page_pic %}
<img
  class= "hero"
  alt="Me and friend"
  src= "{{ site.author.friendPhoto | relative_url }}"
  srcset="{{ site.author.friendPhoto2x | relative_url }} 2x"
/>
{% endcapture %}
