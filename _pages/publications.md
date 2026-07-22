---
layout: page
permalink: /publications/
title: Research & Publications
nav: true
nav_order: 1
---

<div class="research">
  <section class="research-section">
    <h2>Publications</h2>
    <div class="pubcards">
      {% bibliography %}
    </div>
  </section>

  <section class="research-section">
    <h2>Ongoing Research</h2>
    <div class="pubcards">
      {% bibliography -f ongoing %}
    </div>
  </section>
</div>

<style>
  /* The page title is redundant here (the two section headings carry it). */
  .post-header {
    display: none;
  }

  .research-section {
    margin-top: 2.75rem;
  }
  .research-section:first-child {
    margin-top: 0.5rem;
  }
  .research-section > h2 {
    font-family: "Fraunces", Georgia, serif;
    font-size: 1.6rem;
    font-weight: 600;
    border-bottom: 1px solid var(--global-divider-color);
    padding-bottom: 0.4rem;
    margin-bottom: 1.5rem;
  }

  /* jekyll-scholar wraps entries in <ol class="bibliography"><li>…</li></ol> */
  .pubcards ol.bibliography {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  .pubcards ol.bibliography li {
    margin-bottom: 1.1rem;
  }
  .pubcards ol.bibliography li:last-child {
    margin-bottom: 0;
  }

  /* --- Publication card --- */
  .pubcard {
    display: block;
    background: var(--global-card-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 0.55rem;
    padding: 1.3rem 1.5rem;
    transition: border-color 0.18s ease, box-shadow 0.18s ease;
  }
  .pubcard:hover {
    border-color: var(--global-theme-color);
    box-shadow: 0 3px 14px rgba(0, 0, 0, 0.07);
  }

  .pubcard__tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 0.9rem;
  }
  .pubcard__type,
  .pubcard__venue {
    font-family: monospace;
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.02em;
    padding: 0.3rem 0.65rem;
    border-radius: 999px;
    white-space: nowrap;
  }
  .pubcard__type {
    background: color-mix(in srgb, var(--global-theme-color) 14%, transparent);
    color: var(--global-theme-color);
  }
  .pubcard__venue {
    border: 1px solid var(--global-divider-color);
    color: var(--global-text-color-light);
  }
  .pubcard__venue--link {
    color: var(--global-theme-color);
    border-color: color-mix(in srgb, var(--global-theme-color) 45%, transparent);
  }
  .pubcard__venue--link:hover {
    background: var(--global-theme-color);
    color: var(--global-hover-text-color);
    text-decoration: none;
  }
  .pubcard__ext {
    margin-left: 0.25rem;
  }

  .pubcard__title {
    font-size: 1.15rem;
    font-weight: 600;
    line-height: 1.35;
    margin: 0 0 0.45rem;
    color: var(--global-text-color);
  }
  .pubcard__authors {
    font-size: 0.88rem;
    line-height: 1.5;
    color: var(--global-text-color-light);
    margin: 0 0 0.7rem;
  }
  .pubcard__authors strong {
    color: var(--global-text-color);
    font-weight: 600;
  }
  .pubcard__abstract {
    font-size: 0.9rem;
    line-height: 1.55;
    color: var(--global-text-color-light);
    margin: 0 0 0.9rem;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  .pubcard__abslabel {
    font-weight: 600;
    color: var(--global-text-color);
  }
  .pubcard__more {
    font-family: monospace;
    font-size: 0.82rem;
    color: var(--global-theme-color);
  }
  .pubcard__more:hover {
    text-decoration: underline;
  }
</style>
