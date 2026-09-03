---
layout: page
title: Reliable Natural-Language Analytics
description: A validation-first architecture for asking questions about public-sector analytical data in natural language.
importance: 4
featured: true
domain: Applied AI · Research engineering
approach: Ground, generate, validate, execute with restricted access, then choose a verified presentation.
card_steps: [Ground the question, Validate the candidate, Restrict execution]
tech: [Python, FastAPI, Pydantic, PostgreSQL, SQLGlot, Docker Compose]
---

<p class="project-intro">
  In my current work, I develop an internal applied AI system for querying public-sector analytical
  data in natural language. I describe only the non-confidential architecture and engineering
  principles here; I do not include private schemas, data, URLs, screenshots, or performance claims.
</p>

<ol class="system-flow" aria-label="Reliable natural-language analytics architecture">
  <li>Natural-language question</li>
  <li>Ontology and schema grounding</li>
  <li>LLM-generated candidate SQL</li>
  <li>Structural and schema validation</li>
  <li>Restricted read-only execution</li>
  <li>Validated result and visualization</li>
</ol>

<section class="project-section">
  <h2>Problem</h2>
  <p>
    Syntactically valid SQL is not sufficient. A generated query can reference the wrong concepts,
    violate access rules, exceed operational bounds, or produce a misleading presentation.
  </p>
</section>

<section class="project-section">
  <h2>Why it matters</h2>
  <p>
    The system connects model behavior, data semantics, database permissions, and user interpretation.
    Each of these layers can introduce a failure, so I treat reliability as a property of the whole
    path rather than of a single prompt or model response.
  </p>
</section>

<section class="project-section">
  <h2>Approach</h2>
  <p>
    I ground each question in an ontology and the available schema before the model proposes a structured
    query. Independent checks examine the SQL structure and schema references. A restricted read-only role
    executes the validated query within defined bounds. Visualization selection is deterministic or validated separately.
  </p>
</section>

<section class="project-section">
  <h2>Evaluation and evidence</h2>
  <p>
    I use reproducible test cases, provider comparisons, failure analysis, and regression tests. Structured
    outputs and deterministic fallbacks reduce ambiguity in parts of the system that do not require model flexibility.
  </p>
  <div class="evidence-block">
    <strong>Engineering principle:</strong> treat model-generated output as untrusted until it has been independently validated.
  </div>
</section>

<section class="project-section">
  <h2>Technical implementation</h2>
  <p>
    My work spans stakeholder requirements, data ingestion, PostgreSQL modeling, ontology
    and schema grounding, Text-to-SQL, FastAPI and Pydantic services, REST APIs and WebSockets, Metabase
    and frontend integration, containerized deployment, testing, security controls, and operational support.
  </p>
  <p>
    Technologies used across the system may include PostgreSQL, pgvector, SQLGlot, Gemini, Ollama,
    Redis or Valkey, Docker Compose, Nginx, and GitHub Actions. Their roles are architectural, not a claim
    about scale, certification, uptime, or guaranteed correctness.
  </p>
</section>

<section class="project-section">
  <h2>Engineering principle</h2>
  <p>
    I treat model-generated output as untrusted until the surrounding system has grounded, validated,
    and constrained it. Permissions, execution bounds, fallbacks, and regression tests are part of the
    AI feature rather than supporting details.
  </p>
</section>
