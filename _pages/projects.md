---
layout: page
title: Projects
permalink: /projects/
nav: true
nav_order: 2
---

<div class="projects-page">
  <section class="proj-section">
    <h2>Undergraduate Projects</h2>
    <div class="projcards">
      {% assign ug_projects = site.projects | where: "category", "undergraduate" | sort: "importance" %}
      {% for project in ug_projects %}
        <a class="projcard" href="{{ project.url | relative_url }}">
          {% if project.tech %}
            <div class="projcard__tags">
              {% for t in project.tech %}<span class="projcard__tag">{{ t }}</span>{% endfor %}
            </div>
          {% endif %}
          <h3 class="projcard__title">{{ project.title }}</h3>
          <p class="projcard__desc">{{ project.description }}</p>
          <span class="projcard__more">Read More <span aria-hidden="true">&#8594;</span></span>
        </a>
      {% endfor %}
    </div>
  </section>

  <section class="proj-section">
    <h2>Personal Projects</h2>
    {% assign personal_projects = site.projects | where: "category", "personal" | sort: "importance" %}
    {% if personal_projects.size > 0 %}
      <div class="projcards">
        {% for project in personal_projects %}
          <a class="projcard" href="{{ project.url | relative_url }}">
            {% if project.tech %}
              <div class="projcard__tags">
                {% for t in project.tech %}<span class="projcard__tag">{{ t }}</span>{% endfor %}
              </div>
            {% endif %}
            <h3 class="projcard__title">{{ project.title }}</h3>
            <p class="projcard__desc">{{ project.description }}</p>
            <span class="projcard__more">Read More <span aria-hidden="true">&#8594;</span></span>
          </a>
        {% endfor %}
      </div>
    {% else %}
      <p class="proj-empty">Nothing here yet.</p>
    {% endif %}
  </section>
</div>

<style>
  /* The two section headings carry the page identity, so hide the redundant title. */
  .post-header {
    display: none;
  }

  .proj-section {
    margin-top: 2.75rem;
  }
  .proj-section:first-child {
    margin-top: 0.5rem;
  }
  .proj-section > h2 {
    font-family: "Fraunces", Georgia, serif;
    font-size: 1.6rem;
    font-weight: 600;
    border-bottom: 1px solid var(--global-divider-color);
    padding-bottom: 0.4rem;
    margin-bottom: 1.5rem;
  }

  .projcards {
    display: flex;
    flex-direction: column;
    gap: 1.1rem;
  }
  .projcard {
    display: block;
    background: var(--global-card-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 0.55rem;
    padding: 1.3rem 1.5rem;
    text-decoration: none;
    transition: border-color 0.18s ease, box-shadow 0.18s ease;
  }
  .projcard:hover {
    border-color: var(--global-theme-color);
    box-shadow: 0 3px 14px rgba(0, 0, 0, 0.07);
    text-decoration: none;
  }
  .projcard__tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    margin-bottom: 0.75rem;
  }
  .projcard__tag {
    font-family: monospace;
    font-size: 0.68rem;
    letter-spacing: 0.02em;
    padding: 0.25rem 0.6rem;
    border-radius: 999px;
    background: color-mix(in srgb, var(--global-theme-color) 12%, transparent);
    color: var(--global-theme-color);
    white-space: nowrap;
  }
  .projcard__title {
    font-size: 1.15rem;
    font-weight: 600;
    line-height: 1.35;
    margin: 0 0 0.4rem;
    color: var(--global-text-color);
  }
  .projcard:hover .projcard__title {
    color: var(--global-theme-color);
  }
  .projcard__desc {
    font-size: 0.9rem;
    line-height: 1.55;
    color: var(--global-text-color-light);
    margin: 0 0 0.9rem;
  }
  .projcard__more {
    font-family: monospace;
    font-size: 0.82rem;
    color: var(--global-theme-color);
  }

  .proj-empty {
    color: var(--global-text-color-light);
    font-size: 0.95rem;
  }

  /* Detail-page back link (rendered on each project page). */
  .project-back {
    font-family: monospace;
    font-size: 0.82rem;
    margin-bottom: 1.5rem;
  }
</style>
