---
title: "News"
layout: textlay
excerpt: "Zhaofeng Peng from UMass Amherst."
sitemap: false
permalink: /allnews.html
---

# News

<!--{% for article in site.data.news %}
<p>{{ article.date }} <br> {{ article.headline | markdownify}}</p>
{% endfor %}-->


{% for article in site.data.news %}
{{ article.date }}<br>
{{ article.headline | markdownify | strip_newlines }}
{% endfor %}
