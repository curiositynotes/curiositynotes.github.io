---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% assign journals = site.publications | where: "category", "journal" | sort: "date" | reverse %}
{% assign patents = site.publications | where: "category", "patent" | sort: "date" | reverse %}

<style>
.venue-text {
  font-style: italic;
  font-weight: 300;
  color: var(--text-muted-color, #aaa); /* uses theme variable or fallback for dark mode */
}
</style>

<h2>Journal Articles</h2>
<ul>
{% for post in journals %}
  <li>
    {% if post.cover_image %}
      <img src="{{ post.cover_image }}" alt="Journal Cover" style="max-width:200px; margin-bottom:10px;">
    {% endif %}
    
    {% if post.paperurl %}
      <strong><a href="{{ post.paperurl }}">{{ post.title }}</a></strong>
    {% else %}
      <strong>{{ post.title }}</strong>
    {% endif %}
    <br>
    {{ post.authors | replace: "A. Dehkordi", "<strong>A. Dehkordi</strong>" }}<br>
    {% if post.venue %}
      <span class="venue-text">{{ post.venue }}</span>
    {% endif %}
  </li>
{% endfor %}
</ul>

<h2>Patents</h2>
<ul>
{% for post in patents %}
  <li>
    {% if post.patenturl %}
      <strong><a href="{{ post.patenturl }}">{{ post.title }}</a></strong>
    {% else %}
      <strong>{{ post.title }}</strong>
    {% endif %}
    <br>
    {{ post.authors | replace: "A. Dehkordi", "<strong>A. Dehkordi</strong>" }}<br>
    {% if post.venue %}
      <span class="venue-text">{{ post.venue }}</span>
    {% endif %}
  </li>
{% endfor %}
</ul>
