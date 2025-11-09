---
layout: default
title: Inicio
---

<div class="hero-neo">
  <h1>▮ BOLTER-DIGITAL</h1>
  <p class="muted">Registro diario de experimentos, notas y hallazgos en ciberseguridad.</p>
</div>

<section class="posts-grid">
  {% for post in site.posts %}
  <article class="terminal-card">
    <header>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
    </header>

    {% if post.image %}
    <figure class="post-thumb">
      <img src="{{ post.image }}" alt="{{ post.title }}">
    </figure>
    {% endif %}

    <div class="excerpt">
      {{ post.excerpt | strip_html | truncate: 160 }}
    </div>

    <footer class="card-meta">
      <span class="tag">#diario</span>
      <a class="read-more" href="{{ post.url | relative_url }}">Leer →</a>
    </footer>
  </article>
  {% endfor %}
</section>
