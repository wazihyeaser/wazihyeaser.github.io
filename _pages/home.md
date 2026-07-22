---
layout: about
title: Home
permalink: /

selected_papers: false # replaced by the curated Featured strips below
social: false # rendered manually in the hero below

announcements:
  enabled: false # replaced by the curated Featured strips below

latest_posts:
  enabled: false
---

<!-- Custom hero. The theme's default header + profile block are hidden via the
     <style> below; the whole hero is built here for full control. -->
<div class="hero">
  <div class="hero__greeting">
    <p class="hero__hi">Hi, I'm</p>
    <h1 class="hero__name">Wazih Yeaser Tanzim</h1>
    <p class="hero__roles">Research Assistant @ BUET &nbsp;·&nbsp; ML Engineer @ Shottify</p>
  </div>

  <div class="hero__row">
    <div class="hero__image">
      <img src="/assets/img/prof_pic_portrait.png" alt="Wazih Yeaser Tanzim" loading="eager" />
    </div>
    <div class="hero__desc">
      <p>
        I am a research assistant at BUET, where I develop learned precoders for <strong>cell-free massive MIMO</strong>
        in <strong>terahertz (THz)</strong> communication systems. My undergraduate thesis introduced a
        deep-learning-aided hybrid beamformer for multi-user MIMO terahertz communication.
      </p>
      <p>
        My research interests span cell-free MIMO, beamforming, reconfigurable intelligent surfaces (RIS), integrated
        sensing and communication (ISAC), holographic MIMO, and 6G wireless communication, along with fast solvers for
        the convex and non-convex optimization problems these systems demand. I am always open to research
        collaborations that align with these interests, and I am <strong>currently seeking PhD positions</strong>.
      </p>
      <p>
        Alongside my research, I work as an <strong>ML Engineer at Shottify</strong>, where I use large language models
        to build automated pipelines that analyze multimodal web content — interpreting its context, intent, and tone —
        to measure how relevant it is to a given interest.
      </p>
    </div>
  </div>

  {% assign s = site.data.socials %}
  <div class="social hero__social">
    <div class="contact-icons">
      {% if s.email %}<a href="mailto:{{ s.email }}" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
      {% if s.github_username %}<a href="https://github.com/{{ s.github_username }}" title="GitHub" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-github"></i></a>{% endif %}
      {% if s.linkedin_username %}<a href="https://www.linkedin.com/in/{{ s.linkedin_username }}" title="LinkedIn" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
      {% if s.scholar_userid %}<a href="https://scholar.google.com/citations?user={{ s.scholar_userid }}" title="Google Scholar" target="_blank" rel="noopener noreferrer"><i class="ai ai-google-scholar"></i></a>{% endif %}
      {% if s.orcid_id %}<a href="https://orcid.org/{{ s.orcid_id }}" title="ORCID" target="_blank" rel="noopener noreferrer"><i class="ai ai-orcid"></i></a>{% endif %}
    </div>
  </div>
</div>

<style>
  /* Hide the theme's default header + profile; the hero above replaces them. */
  .post-header { display: none; }
  .profile { display: none; }

  /* --- Hero greeting (centered) --- */
  .hero__greeting {
    text-align: center;
    margin-bottom: 1rem;
  }
  .hero__hi {
    color: var(--global-text-color);
    font-size: 1.75rem;
    font-weight: 700;
    letter-spacing: 0.02em;
    margin: 0 0 0.4rem;
  }
  .hero__name {
    font-family: "Fraunces", Georgia, "Times New Roman", serif;
    font-weight: 600;
    font-size: clamp(2rem, 5vw, 3rem);
    letter-spacing: -0.015em;
    line-height: 1.1;
    margin: 0;
  }
  .hero__roles {
    color: var(--global-text-color-light);
    font-size: 1.15rem;
    font-weight: 700;
    font-style: italic;
    margin: 0.6rem 0 0;
  }

  /* --- Hero row: large image left, description right (vertically centered) --- */
  .hero__row {
    display: flex;
    align-items: center;
    gap: 2.25rem;
    margin-top: 2rem;
  }
  .hero__image {
    flex: 0 0 auto;
    width: min(320px, 42%);
  }
  .hero__image img {
    width: 100%;
    aspect-ratio: 848 / 1264; /* tall portrait, matches the photo (no crop) */
    object-fit: cover;
    border-radius: 1rem; /* rounded corners */
    box-shadow: 0 2px 5px #00000029, 0 2px 10px #0000001f;
    display: block;
  }
  .hero__desc {
    flex: 1;
    font-style: italic; /* bio set in italic */
  }
  .hero__desc p {
    margin-bottom: 1rem;
  }
  .hero__desc p:last-child {
    margin-bottom: 0;
  }
  @media (max-width: 575px) {
    .hero__row {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    .hero__image {
      width: min(240px, 70%);
    }
  }

  /* --- Social icons: centered under the hero, web-standard 24px --- */
  .hero__social {
    margin-top: 2.5rem;
  }
  .social .contact-icons {
    font-size: 1.5rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
    line-height: 1;
  }
  .social .contact-icons a i::before {
    transition: color 0.2s ease-in-out;
  }

  /* --- Featured strips --- */
  .featured {
    clear: both;
    margin-top: 3rem;
  }
  .featured-strip {
    margin-bottom: 2rem;
  }
  .featured-strip__head {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 1rem;
    border-bottom: 1px solid var(--global-divider-color);
    padding-bottom: 0.4rem;
    margin-bottom: 1rem;
  }
  .featured-strip__title {
    font-family: "Fraunces", Georgia, serif;
    font-size: 1.5rem;
    font-weight: 600;
    margin: 0;
  }
  .featured-strip__all {
    font-size: 0.85rem;
    white-space: nowrap;
  }
  .featured-strip__all:hover {
    text-decoration: none;
  }
  .featured-row {
    display: flex;
    gap: 1rem;
    overflow-x: auto;
    scroll-snap-type: x proximity;
    padding-bottom: 0.6rem;
    scrollbar-width: thin;
    -webkit-overflow-scrolling: touch;
  }
  .featured-row::-webkit-scrollbar {
    height: 6px;
  }
  .featured-row::-webkit-scrollbar-thumb {
    background: var(--global-divider-color);
    border-radius: 3px;
  }
  .fcard {
    flex: 0 0 auto;
    width: min(280px, 78vw);
    scroll-snap-align: start;
    display: flex;
    flex-direction: column;
    background-color: var(--global-card-bg-color);
    border-radius: 0.35rem;
    overflow: hidden;
    box-shadow: 0 2px 5px #00000029, 0 2px 10px #0000001f;
    text-decoration: none;
    transition: transform 0.22s ease, box-shadow 0.22s ease;
  }
  .fcard:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 22px rgba(0, 0, 0, 0.12), 0 4px 10px rgba(0, 0, 0, 0.1);
    text-decoration: none;
  }
  @media (prefers-reduced-motion: reduce) {
    .fcard { transition: none; }
    .fcard:hover { transform: none; }
  }
  .fcard__img {
    height: 140px;
    background-size: cover;
    background-position: center;
    background-color: var(--global-divider-color);
  }
  .fcard__body {
    padding: 0.9rem 1rem 1.1rem;
  }
  .fcard__title {
    font-size: 1rem;
    font-weight: 500;
    line-height: 1.3;
    margin: 0;
    color: var(--global-text-color);
  }
  .fcard:hover .fcard__title {
    color: var(--global-theme-color);
  }
  .fcard__meta {
    font-size: 0.72rem;
    letter-spacing: 0.03em;
    text-transform: uppercase;
    color: var(--global-theme-color);
    margin: 0.45rem 0 0;
  }
  .fcard__blurb {
    font-size: 0.85rem;
    line-height: 1.5;
    color: var(--global-text-color-light);
    margin: 0.5rem 0 0;
  }
  .fcard--empty {
    justify-content: center;
    align-items: center;
    min-height: 120px;
    border: 1px dashed var(--global-divider-color);
    box-shadow: none;
    background-color: transparent;
    cursor: default;
  }
  .fcard--empty:hover {
    transform: none;
    box-shadow: none;
  }
  .fcard--empty .fcard__title {
    color: var(--global-text-color-light);
    font-weight: 400;
  }
</style>

<section class="featured" aria-label="Featured work">
  {% for strip in site.data.featured %}
  <div class="featured-strip">
    <div class="featured-strip__head">
      <h2 class="featured-strip__title">{{ strip.heading }}</h2>
      {% if strip.view_all %}<a class="featured-strip__all" href="{{ strip.view_all | relative_url }}">View all &rarr;</a>{% endif %}
    </div>

    <div class="featured-row" tabindex="0" aria-label="{{ strip.heading }} highlights">
      {% if strip.items and strip.items.size > 0 %}
        {% for item in strip.items %}
          <a class="fcard" href="{{ item.link | default: strip.view_all | relative_url }}">
            {% if item.image %}<div class="fcard__img" style="background-image: url('{{ item.image | prepend: '/' | relative_url }}');"></div>{% endif %}
            <div class="fcard__body">
              <h3 class="fcard__title">{{ item.title }}</h3>
              {% if item.meta %}<p class="fcard__meta">{{ item.meta }}</p>{% endif %}
              {% if item.blurb %}<p class="fcard__blurb">{{ item.blurb }}</p>{% endif %}
            </div>
          </a>
        {% endfor %}
      {% else %}
        <div class="fcard fcard--empty">
          <div class="fcard__body">
            <h3 class="fcard__title">Nothing yet.</h3>
          </div>
        </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</section>
