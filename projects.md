---
layout: page
title: Research
permalink: /projects/
body_class: research-page
---

{% assign projects = site.data.projects %}
{% assign theme_co = "Co-Creative Systems" %}
{% assign theme_well = "AI & Well-being" %}
{% assign theme_comp = "Computational Creativity" %}

<div class="projects-page">
  <div class="projects-intro-grid">
    <p class="editorial-index">FIELD NOTES / 2025—2026</p>
    <p class="projects-intro">
      I study how AI-mediated creative systems can create space for reflection, emotional depth, and human agency—often by designing friction instead of removing it.
    </p>
  </div>

  {% if projects.size > 0 %}
    <section class="project-theme-group" aria-labelledby="theme-co-title">
      <header class="project-theme-heading">
        <span>01</span>
        <h2 id="theme-co-title">{{ theme_co }}</h2>
      </header>
      <div class="projects-grid">
        {% for p in projects %}
          {% if p.theme == theme_co %}
          <article class="project-card{% if p.flagship %} is-flagship{% endif %}">
            {% if p.image and p.image != "" %}
            <a class="project-card-image" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}" aria-label="Read {{ p.name }} case study">
              <img src="{{ p.image | relative_url }}" alt="" loading="{% if p.flagship %}eager{% else %}lazy{% endif %}">
            </a>
            {% endif %}
            <div class="project-card-content">
              <p class="project-period">{{ p.period }}{% if p.role %} · {{ p.role }}{% endif %}</p>
              <h3 class="project-title">
                <a href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">{{ p.name }}</a>
              </h3>
              {% if p.brief %}<p class="project-brief">{{ p.brief }}</p>{% endif %}
              {% if p.insight %}<p class="project-insight"><span>Key insight</span>{{ p.insight }}</p>{% endif %}
              <a class="text-arrow" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">Read case study <span>→</span></a>
            </div>
          </article>
          {% endif %}
        {% endfor %}
      </div>
    </section>

    <section class="project-theme-group" aria-labelledby="theme-well-title">
      <header class="project-theme-heading">
        <span>02</span>
        <h2 id="theme-well-title">{{ theme_well }}</h2>
      </header>
      <div class="projects-grid">
        {% for p in projects %}
          {% if p.theme == theme_well %}
          <article class="project-card">
            {% if p.image and p.image != "" %}
            <a class="project-card-image" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}" aria-label="Read {{ p.name }} case study">
              <img src="{{ p.image | relative_url }}" alt="" loading="lazy">
            </a>
            {% endif %}
            <div class="project-card-content">
              <p class="project-period">{{ p.period }}{% if p.role %} · {{ p.role }}{% endif %}</p>
              <h3 class="project-title">
                <a href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">{{ p.name }}</a>
              </h3>
              {% if p.brief %}<p class="project-brief">{{ p.brief }}</p>{% endif %}
              {% if p.insight %}<p class="project-insight"><span>Key insight</span>{{ p.insight }}</p>{% endif %}
              <a class="text-arrow" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">Read case study <span>→</span></a>
            </div>
          </article>
          {% endif %}
        {% endfor %}
      </div>
    </section>

    <section class="project-theme-group" aria-labelledby="theme-comp-title">
      <header class="project-theme-heading">
        <span>03</span>
        <h2 id="theme-comp-title">{{ theme_comp }}</h2>
      </header>
      <div class="projects-grid">
        {% for p in projects %}
          {% if p.theme == theme_comp %}
          <article class="project-card">
            {% if p.image and p.image != "" %}
            <a class="project-card-image" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}" aria-label="Read {{ p.name }} case study">
              <img src="{{ p.image | relative_url }}" alt="" loading="lazy">
            </a>
            {% endif %}
            <div class="project-card-content">
              <p class="project-period">{{ p.period }}{% if p.role %} · {{ p.role }}{% endif %}</p>
              <h3 class="project-title">
                <a href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">{{ p.name }}</a>
              </h3>
              {% if p.brief %}<p class="project-brief">{{ p.brief }}</p>{% endif %}
              {% if p.insight %}<p class="project-insight"><span>Key insight</span>{{ p.insight }}</p>{% endif %}
              <a class="text-arrow" href="{{ '/research/' | append: p.slug | append: '/' | relative_url }}">Read case study <span>→</span></a>
            </div>
          </article>
          {% endif %}
        {% endfor %}
      </div>
    </section>
  {% else %}
    <p>No projects yet. Add entries in <code>_data/projects.yml</code>.</p>
  {% endif %}
</div>
