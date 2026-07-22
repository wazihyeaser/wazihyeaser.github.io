---
layout: default
permalink: /blog/
title: Blog
nav: true
nav_order: 3
---

<div class="post">
  <header class="post-header">
    <h1 class="post-title">Blog</h1>
  </header>

  <article>
    <!-- Category filter bar — auto-derived from the categories used across posts.
         Add a post with a new category and it appears here automatically. -->
    <div class="blog-filter" aria-label="Filter posts by category">
      <button class="blog-filter__pill is-active" type="button" data-filter="all">All</button>
      {% assign cats = site.categories | sort %}
      {% for category in cats %}
        <button class="blog-filter__pill" type="button" data-filter="{{ category[0] | slugify }}">{{ category[0] | capitalize }}</button>
      {% endfor %}
    </div>

    <!-- Card grid -->
    <div class="blog-grid">
      {% for post in site.posts %}
        {% assign cat = post.categories | first %}
        {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
        {% assign year = post.date | date: "%Y" %}
        <a class="blog-card" href="{{ post.url | relative_url }}" data-category="{{ cat | slugify }}">
          {% if post.thumbnail %}
            <div class="blog-card__img{% if post.thumbnail_contain %} blog-card__img--contain{% endif %}" style="background-image: url('{{ post.thumbnail | relative_url }}');"></div>
          {% endif %}
          <div class="blog-card__body">
            <h2 class="blog-card__title">{{ post.title }}</h2>
            {% if post.description %}<p class="blog-card__desc">{{ post.description }}</p>{% endif %}
            <p class="blog-card__meta">
              {{ year }}{% if cat %} &middot; {{ cat | capitalize }}{% endif %} &middot; {{ read_time }} min read
            </p>
          </div>
        </a>
      {% endfor %}
    </div>

    <p class="blog-empty" hidden>Nothing here yet.</p>
  </article>
</div>

<style>
  .blog-filter {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin: 1.5rem 0 2rem;
  }
  .blog-filter__pill {
    font-family: inherit;
    font-size: 0.8rem;
    padding: 0.35rem 0.9rem;
    border-radius: 999px;
    border: 1px solid var(--global-divider-color);
    background: transparent;
    color: var(--global-text-color);
    cursor: pointer;
    transition: color 0.15s ease, border-color 0.15s ease, background-color 0.15s ease;
  }
  .blog-filter__pill:hover {
    border-color: var(--global-theme-color);
    color: var(--global-theme-color);
  }
  .blog-filter__pill.is-active {
    background: var(--global-theme-color);
    border-color: var(--global-theme-color);
    color: var(--global-hover-text-color);
  }

  .blog-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.5rem;
  }
  .blog-card {
    display: flex;
    flex-direction: column;
    overflow: hidden;
    background: var(--global-card-bg-color);
    border-radius: 0.4rem;
    box-shadow: 0 2px 5px #00000029, 0 2px 10px #0000001f;
    text-decoration: none;
    transition: transform 0.22s ease, box-shadow 0.22s ease;
  }
  .blog-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 22px rgba(0, 0, 0, 0.12), 0 4px 10px rgba(0, 0, 0, 0.1);
    text-decoration: none;
  }
  @media (prefers-reduced-motion: reduce) {
    .blog-card { transition: none; }
    .blog-card:hover { transform: none; }
  }
  .blog-card__img {
    height: 180px;
    background-size: cover;
    background-position: center;
    background-color: var(--global-divider-color);
  }
  /* Portrait covers (e.g. book reviews): show the whole image, centered. */
  .blog-card__img--contain {
    background-size: contain;
    background-repeat: no-repeat;
  }
  .blog-card__body {
    padding: 1.1rem 1.2rem 1.3rem;
  }
  .blog-card__title {
    font-size: 1.15rem;
    font-weight: 500;
    line-height: 1.3;
    margin: 0;
    color: var(--global-text-color);
  }
  .blog-card:hover .blog-card__title {
    color: var(--global-theme-color);
  }
  .blog-card__desc {
    font-size: 0.9rem;
    line-height: 1.5;
    color: var(--global-text-color-light);
    margin: 0.5rem 0 0;
  }
  .blog-card__meta {
    font-size: 0.75rem;
    color: var(--global-text-color-light);
    margin: 0.9rem 0 0;
  }
  .blog-empty {
    text-align: center;
    color: var(--global-text-color-light);
    padding: 2.5rem 0;
  }
</style>

<script>
  (function () {
    var pills = document.querySelectorAll('.blog-filter__pill');
    var cards = document.querySelectorAll('.blog-card');
    var empty = document.querySelector('.blog-empty');
    function apply(filter) {
      var shown = 0;
      cards.forEach(function (c) {
        var match = filter === 'all' || c.getAttribute('data-category') === filter;
        c.style.display = match ? '' : 'none';
        if (match) shown++;
      });
      if (empty) empty.hidden = shown !== 0;
    }
    pills.forEach(function (p) {
      p.addEventListener('click', function () {
        pills.forEach(function (x) { x.classList.remove('is-active'); });
        p.classList.add('is-active');
        apply(p.getAttribute('data-filter'));
      });
    });
  })();
</script>
