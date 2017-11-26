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

## Preface
Hi,

My name is Kiet Tran. I am a junior studying mechanical engineering at the University of Minnesota, Twin Cities. I am hoping to build a career in mechatronics or aerospace industry in the near future. This blog shows the projects and activities that I was or currently is involved in.
</div>
