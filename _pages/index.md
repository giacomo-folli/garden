---
layout: home
title: Home
id: home
permalink: /
---

<!-- # Welcome! 🌱 -->
# Hi, Paco here 🌱
<!-- 24 year old something guy. -->


<br />
> Take a look at <span style="font-weight: bold"> [[Primo]] </span> to get started on your exploration.

<br />

<strong>Recently updated notes</strong>

{% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
{% for note in recent_notes limit: 5 %}

\# {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>

{% endfor %}
