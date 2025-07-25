---
layout: home
title: Home
id: home
permalink: /
---

# Hi, Paco here 🌱

<br />
> Take a look at <span style="font-weight: bold"> [[Primo]] </span> to get started on your exploration.

<br />

<strong>Recently updated notes</strong>

{% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
{% for note in recent_notes limit: 5 %}

\# {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>

{% endfor %}

<strong>Tags</strong>

{% assign all_tags = "" | split: "" %}
{% for item in site.notes %}
  {% for tag in item.tags %}
    {% unless all_tags contains tag %}
      {% assign all_tags = all_tags | push: tag %}
    {% endunless %}
  {% endfor %}
{% endfor %}

<ul>
  {% for tag in all_tags %}
    <li><a href="/tags/{{ tag | slugify }}/">{{ tag }}</a></li>
  {% endfor %}
</ul>
