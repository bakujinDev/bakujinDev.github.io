---
layout: page
title: 프로젝트
permalink: /projects/
---

{% for project in site.data.projects %}
<section class="project">
  <h2 class="project-name">
    {{ project.name }}
    <span class="project-status project-status--{{ project.status }}">{{ project.status }}</span>
  </h2>
  <p class="project-blurb">{{ project.blurb }}</p>
  <ul class="project-post-list">
    {% assign posts = site.categories[project.slug] | reverse %}
    {% for post in posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
    </li>
    {% endfor %}
  </ul>
</section>
{% endfor %}
