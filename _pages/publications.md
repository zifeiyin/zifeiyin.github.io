---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can also find my articles on <u><a href="https://scholar.google.com/citations?user=your-id">my Google Scholar profile</a>.</u>

{% include base_path %}

{% comment %}
  This part groups all the publications by year and sorts them
{% endcomment %}
{% assign publications_by_year = site.publications | reverse | group_by_exp:"item", "item.date | date: '%Y'" %}

{% for group in publications_by_year %}
  <h2 class="archive__subtitle">{{ group.name }}</h2>
  <hr>
  <ul>
  {% for publication in group.items %}
    <li>
      {% comment %}
        This include will render the details of each paper.
        You'll need an 'archive-single.html' file to display the paper's info.
      {% endcomment %}
      {% include archive-single.html %}
    </li>
  {% endfor %}
  </ul>
{% endfor %}
