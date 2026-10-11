---
layout: page
title: Practice
permalink: /creative/
body_class: practice-page
---

<div class="creative-page">
<p class="practice-framing">{{ site.data.creative.framing }}</p>

<header class="practice-section-heading">
  <p class="editorial-index">01 / MOVING IMAGE</p>
  <h2>Film</h2>
</header>

{% assign films = site.data.creative.films %}
{% if films and films.size > 0 %}
  <div class="creative-list creative-list-paper creative-list-film">
    {% for film in films %}
    <article class="creative-item film-entry film-teaser"{% if film.rotation %} data-paper-tilt style="--paper-tilt: {{ film.rotation }}deg"{% endif %}>
      <a class="film-card-link" href="{{ film.url | relative_url }}">
        <h3>{{ film.title }}</h3>
        {% if film.slate %}
        <div class="film-slate">
          <div class="film-slate-line">
            <span>{{ film.title | upcase }}</span>
            <span>{{ film.slate.roll }}</span>
          </div>
          <div class="film-slate-line">
            <span>{{ film.slate.credits }}</span>
            <span>{{ film.slate.dates }}</span>
          </div>
        </div>
        {% else %}
        <div class="zine-meta">{{ film.role }}</div>
        <div class="zine-meta">{{ film.place }} · {{ film.period }}</div>
        {% endif %}

        {% if film.photos and film.photos.size > 0 %}
        <div class="film-photo-grid film-photo-grid-teaser" aria-label="Preview stills">
          {% for photo in film.photos limit: 2 %}
          <img src="{{ photo | relative_url }}" alt="Still from {{ film.title }}" loading="lazy">
          {% endfor %}
        </div>
        {% endif %}

        <p class="film-teaser-blurb">{{ film.synopsis }}</p>
        <p class="creative-link-wrap film-teaser-cta"><span>View stills &amp; script →</span></p>
      </a>
    </article>
    {% endfor %}
  </div>
{% endif %}

<header class="practice-section-heading">
  <p class="editorial-index">02 / TEXT &amp; IMAGE</p>
  <h2>Poetry</h2>
</header>

{% assign poems = site.data.creative.poems %}
{% if poems and poems.size > 0 %}
  <div class="creative-list creative-list-paper creative-list-poetry">
    {% for poem in poems %}
    <article class="creative-item"{% if poem.rotation %} data-paper-tilt style="--paper-tilt: {{ poem.rotation }}deg"{% endif %}>
      <h3>{{ poem.title }}</h3>
      <p>{{ poem.description }}</p>
      <div class="zine-meta">{{ poem.year }} • {{ poem.category }}</div>
      {% if poem.research_note %}
      <p class="creative-research-note">{{ poem.research_note }}</p>
      {% endif %}
      {% if poem.explanation_paragraphs %}
      <details class="creative-explanation">
        <summary>{{ poem.explanation_label | default: "Read explanation" }}</summary>
        <div class="creative-explanation-body">
          {% for paragraph in poem.explanation_paragraphs %}
          <p>{{ paragraph }}</p>
          {% endfor %}
        </div>
      </details>
      {% endif %}
      <p class="creative-link-wrap">
        <a href="{{ poem.file | relative_url }}" target="_blank" rel="noopener noreferrer">Open work (PDF)</a>
      </p>
    </article>
    {% endfor %}
  </div>
{% else %}
  <div class="zine-placeholder">
    <h4>Poetry</h4>
    <p>Add your poetry projects in <code>_data/creative.yml</code>.</p>
  </div>
{% endif %}

<header class="practice-section-heading">
  <p class="editorial-index">03 / FRAGMENTS</p>
  <h2>Zines</h2>
</header>

{% assign zines = site.data.creative.zines %}
{% if zines.size > 0 %}
  <div class="creative-list creative-list-paper creative-list-zines">
  {% for zine in zines %}
  <article class="creative-item"{% if zine.rotation %} data-paper-tilt style="--paper-tilt: {{ zine.rotation }}deg"{% endif %}>
    <h3>{{ zine.title }}</h3>
    <p>{{ zine.description }}</p>
    <div class="zine-meta">{{ zine.year }} • {{ zine.category }}</div>
    {% if zine.research_note %}
    <p class="creative-research-note">{{ zine.research_note }}</p>
    {% endif %}
    {% if zine.explanation_paragraphs %}
    <details class="creative-explanation">
      <summary>{{ zine.explanation_label | default: "Read explanation" }}</summary>
      <div class="creative-explanation-body">
        {% for paragraph in zine.explanation_paragraphs %}
        <p>{{ paragraph }}</p>
        {% endfor %}
      </div>
    </details>
    {% endif %}
    <p class="creative-link-wrap">
      <a href="{{ zine.pdf | relative_url }}" target="_blank" rel="noopener noreferrer">Open work (PDF)</a>
    </p>
  </article>
  {% endfor %}
  </div>
{% else %}
  <div class="zine-placeholder">
    <h4>Zines</h4>
    <p>Add zine entries in <code>_data/creative.yml</code>.</p>
  </div>
{% endif %}
</div>
