---
layout: default
title: Home
permalink: /
description: Rafael Testa develops and evaluates AI systems across computer vision, generative models, natural-language analytics, and machine learning engineering.
---

<article class="portfolio-home">
  <header class="hero">
    <div>
      <p class="eyebrow">Applied AI / Machine Learning Engineer &amp; Researcher</p>
      <h1>Rafael Luiz Testa, PhD</h1>
      <p class="lead">
        I develop and evaluate AI systems in computer vision, generative models,
        natural-language analytics, and machine learning engineering.
      </p>
      <div class="hero-actions" aria-label="Primary links">
        <a class="button-link primary" href="{{ '/projects/' | relative_url }}">Explore selected work</a>
        <a class="button-link" href="{{ '/cv/' | relative_url }}">View CV</a>
      </div>
    </div>
    <aside class="hero-profile" aria-label="Portrait and professional focus">
      <figure class="hero-portrait">
        <img
          src="{{ '/assets/img/rafael-testa.jpeg' | relative_url }}"
          alt="Portrait of Rafael Luiz Testa"
          width="1066"
          height="1600"
          fetchpriority="high"
          decoding="async"
        >
      </figure>
      <div class="hero-aside">
        <p><strong>Computer Vision</strong> · Generative AI</p>
        <p><strong>Reliable AI</strong> · Evaluation</p>
        <p><strong>Research Engineering</strong> · Data systems</p>
      </div>
    </aside>
  </header>

  <section class="home-section" aria-labelledby="themes-heading">
    <div class="section-heading">
      <h2 id="themes-heading">What I work on</h2>
      <p>
        I combine model development with data, software, and evaluation. I focus on
        failures that are easy to miss when a system is assessed only through its final output.
      </p>
    </div>
    <div class="theme-grid">
      <article class="theme-card">
        <p class="eyebrow">01</p>
        <h3>Generative Vision</h3>
        <p>Video synthesis, temporal coherence, facial analysis, and synthetic media.</p>
      </article>
      <article class="theme-card">
        <p class="eyebrow">02</p>
        <h3>Reliable AI Systems</h3>
        <p>LLMs, Text-to-SQL, evaluation, validation, and deterministic fallbacks.</p>
      </article>
      <article class="theme-card">
        <p class="eyebrow">03</p>
        <h3>Research Engineering</h3>
        <p>Reproducible experiments, data systems, backend engineering, and operational reliability.</p>
      </article>
    </div>
  </section>

  <section class="home-section" aria-labelledby="selected-work-heading">
    <div class="section-heading">
      <h2 id="selected-work-heading">Selected work</h2>
      <p>
        These projects cover generative video, facial analysis, deepfake detection, and
        LLM-based analytics. Each project began with a specific failure mode and required
        an implementation and evaluation designed around that failure.
      </p>
    </div>
    <div class="work-grid">
      {% assign sorted_projects = site.projects | sort: 'importance' %}
      {% for project in sorted_projects %}
        {% if project.featured %}
          <article class="work-card">
            <a class="work-card-link" href="{{ project.url | relative_url }}">
              <div class="signal-strip" aria-hidden="true">
                {% for step in project.card_steps %}<span>{{ step }}</span>{% endfor %}
              </div>
              <div class="work-card-body">
                <p class="eyebrow">{{ project.domain }}</p>
                <h3>{{ project.title }}</h3>
                <p>{{ project.description }}</p>
                <ul class="tag-list" aria-label="Technologies">
                  {% for item in project.tech limit: 5 %}<li>{{ item }}</li>{% endfor %}
                </ul>
              </div>
            </a>
          </article>
        {% endif %}
      {% endfor %}
    </div>
  </section>

  <section class="home-section" aria-labelledby="publications-heading">
    <div class="section-heading">
      <h2 id="publications-heading">Selected publications</h2>
      <p>
        My publications cover temporal coherence in generative video, synthetic-media
        analysis, facial-expression synthesis, and efficient facial-expression classification.
      </p>
    </div>
    {% include selected_papers.liquid %}
    <p><a href="{{ '/publications/' | relative_url }}">View all publications →</a></p>
  </section>

  <section class="home-section" aria-labelledby="current-work-heading">
    <div class="section-heading">
      <h2 id="current-work-heading">Current direction</h2>
      <p>
        In my current work, I develop an internal natural-language analytics platform for
        public-sector data. The system grounds questions in data semantics, validates candidate
        SQL, restricts database execution, and checks presentation choices independently.
      </p>
    </div>
    <div class="method-bridge" aria-label="Reliable AI workflow">
      <div><strong>Ground</strong><span>Connect language to schemas and domain concepts.</span></div>
      <div><strong>Generate</strong><span>Produce structured candidates with bounded responsibilities.</span></div>
      <div><strong>Validate</strong><span>Check structure, references, and allowed behavior.</span></div>
      <div><strong>Execute</strong><span>Use restricted roles and bounded operations.</span></div>
      <div><strong>Evaluate</strong><span>Test failures, fallbacks, and regressions.</span></div>
    </div>
  </section>

  <section class="home-section" aria-labelledby="contact-heading">
    <div class="contact-band">
      <div>
        <h2 id="contact-heading">Contact</h2>
        <p>I am available to discuss applied AI, research engineering, and technical collaboration.</p>
      </div>
      <div class="contact-links" aria-label="Professional profiles">
        <a href="https://www.linkedin.com/in/rafaelluiztesta">LinkedIn</a>
        <a href="https://github.com/lapidarioz">GitHub</a>
        <a href="https://scholar.google.com/citations?user=8NCe0IgAAAAJ">Google Scholar</a>
        <a href="https://orcid.org/0000-0002-7209-1111">ORCID</a>
      </div>
    </div>
  </section>
</article>
