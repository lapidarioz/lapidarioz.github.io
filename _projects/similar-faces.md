---
layout: page
title: Facial Expression Synthesis Based on Similar Faces
description: A geometry-aware computer-vision pipeline for retrieving a similar face and transferring an expression.
importance: 2
featured: true
domain: Geometry-aware vision · Research
approach: Similar-face retrieval followed by landmark-guided warping and texture transfer.
card_steps: [Retrieve a reference, Transfer geometry, Evaluate perception]
tech: [Python, OpenCV, dlib, Image retrieval, Facial landmarks, Docker]
github: https://github.com/lapidarioz/emocione
paper: https://link.springer.com/article/10.1007/s11042-021-11525-4
---

<p class="project-intro">
  In this project, I developed a method that retrieves a similar face as a prior and transfers
  its expression geometry and appearance to an input photograph.
</p>

<ol class="system-flow" aria-label="Conceptual expression-synthesis pipeline">
  <li>Input face</li>
  <li>Facial landmarks</li>
  <li>Similar face or reference</li>
  <li>Triangulation and piecewise warping</li>
  <li>Texture transfer and synthesized expression</li>
</ol>

<section class="project-section">
  <h2>Problem</h2>
  <p>
    Expression transfer must change meaningful facial regions without losing the identity and
    visual context of the input image. A purely pixel-level transformation offers little control
    over the structures being moved.
  </p>
</section>

<section class="project-section">
  <h2>Why it matters</h2>
  <p>
    Small geometric errors are easy to perceive in faces. Explicit facial geometry makes the
    transformation easier to inspect and provides a prior for which regions should change.
  </p>
</section>

<section class="project-section">
  <h2>Approach</h2>
  <p>
    I retrieve a suitable similar face, identify facial landmarks, and use
    triangulation with piecewise affine warping to deform facial regions. Expression-ratio,
    illumination, or texture information is then transferred to form the synthesized expression.
  </p>
</section>

<section class="project-section">
  <h2>Evaluation and evidence</h2>
  <p>
    I connected the explicit geometric prior to user or perceptual evaluation because a single
    low-level similarity measure does not establish either geometric correctness or perceived
    expression quality.
  </p>
  <div class="evidence-block">
    <strong>Evaluation focus:</strong> explicit geometry and prior → image transformation → perceptual evaluation.
  </div>
</section>

<section class="project-section">
  <h2>Technical implementation</h2>
  <p>
    Python, OpenCV, and dlib support face retrieval, landmark detection, triangulation, geometric
    transformation, and image composition. Docker captures the execution environment for reproducibility.
  </p>
</section>

<section class="project-section">
  <h2>What I learned</h2>
  <p>
    Encoding facial structure directly made the method and its failures easier to interpret than
    treating the image as an undifferentiated array of pixels.
  </p>
</section>

<div class="project-links">
  <a class="button-link primary" href="https://github.com/lapidarioz/emocione">Code repository</a>
  <a class="button-link" href="https://link.springer.com/article/10.1007/s11042-021-11525-4">Journal article</a>
</div>
