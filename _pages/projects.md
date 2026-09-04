---
layout: page
title: Projects
seo_title: AI & Machine Learning Projects | Rafael Testa
permalink: /projects/
description: Applied AI, computer vision, and machine learning engineering projects by Rafael Testa.
nav: true
nav_order: 2
---

<p class="project-intro">
  My projects span generative video, geometry-aware image synthesis, deepfake detection,
  and LLM-based analytics. For each project, I describe the problem, the implementation,
  and the evidence used to evaluate the relevant behavior.
</p>

<div class="work-grid">
  {% assign sorted_projects = site.projects | sort: 'importance' %}
  {% for project in sorted_projects %}
    {% if project.github %}
      {% assign project_destination = project.github %}
      {% assign project_destination_label = project.title | append: ' GitHub repository' %}
    {% else %}
      {% assign project_destination = project.url | relative_url %}
      {% assign project_destination_label = project.title | append: ' project details' %}
    {% endif %}
    <article class="work-card">
      <a class="work-card-link" href="{{ project_destination }}" aria-label="{{ project_destination_label }}">
        <div class="signal-strip" aria-hidden="true">
          {% for step in project.card_steps %}<span>{{ step }}</span>{% endfor %}
        </div>
        <div class="work-card-body">
          <p class="eyebrow">{{ project.domain }}</p>
          <h2>{{ project.title }}</h2>
          <p>{{ project.description }}</p>
          <p><strong>Approach:</strong> {{ project.approach }}</p>
          <ul class="tag-list" aria-label="Technologies">
            {% for item in project.tech %}<li>{{ item }}</li>{% endfor %}
          </ul>
          <p class="card-destination">
            {% if project.github %}View GitHub repository ↗{% else %}View project details →{% endif %}
          </p>
        </div>
      </a>
    </article>
  {% endfor %}
</div>
