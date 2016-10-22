---
layout: project
page: project
project: F16
title: Gods and Enemies
gods: [Goddess of Priests, God of Artisans, Goddess of Farmers, God of Merchants, Goddess of Servants, God of Warriors]
totallynotcards: [Basics]
---
{% for card in page.totallynotcards %}
{% assign cites = site.cite | where: "page", page.title | where: "title", card | where: "project", page.project %}
{% for c in cites %}
<div class="cite">
<div class="card">
<h2>{{ c.title }}</h2>
{{ c.content | markdownify }}
<div class="tooltip">
{{ c.title }} by {{ c.author | join: ", " }}<br />
<a href="{{ c.url }}">permalink</a><span style="padding-right: 20px;"></span><a href="{{ c.source }}">source</a>
</div>
</div>
</div>
{% endfor %}
{% endfor %}
<div class="card">
<div class="collection">
{% for card in page.gods %}
<a href="{{ card | relative_url | replace: "'",'' | slugify }}" class="collection-item">{{ card }}</a>
{% endfor %}
</div>
</div>