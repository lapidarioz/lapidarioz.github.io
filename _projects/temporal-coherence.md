---
layout: page
title: Temporal Coherence for Facial Video Synthesis
description: Treating temporal coherence as a first-class property in image-to-video facial-expression synthesis.
importance: 1
featured: true
domain: Generative vision · Research
approach: Previous-frame conditioning with pixel-transition and facial-landmark consistency objectives.
card_steps: [Plausible frame, Temporal constraints, Coherent video]
tech: [Python, TensorFlow, Computer vision, GANs, Facial landmarks, Docker]
github: https://github.com/lapidarioz/temporal-coherence
paper: https://doi.org/10.1109/ACCESS.2025.3612820
---

<p class="project-intro">
  In my doctoral research, I found that individually plausible frames could still produce
  videos with flicker or unnatural motion. I therefore treated temporal coherence as a
  separate property rather than assuming that frame-level quality would produce a coherent sequence.
</p>

<ol class="system-flow" aria-label="Conceptual synthesis pipeline">
  <li>Source face and reference expression or video</li>
  <li>Preprocessing and facial geometry</li>
  <li>Generative model</li>
  <li>Temporal and geometric constraints</li>
  <li>Synthetic video and video-oriented evaluation</li>
</ol>

<section class="project-section">
  <h2>Problem</h2>
  <p>
    A frame-wise model can optimize each image without representing the transition between
    consecutive frames. Small discontinuities can then accumulate as visible flicker or
    unnatural facial motion.
  </p>
</section>

<section class="project-section">
  <h2>Why it matters</h2>
  <p>
    Temporal behavior is part of the validity of a generated video. An evaluation based only
    on still frames can miss the instability that viewers perceive when the frames are shown
    as a sequence.
  </p>
</section>

<section class="project-section">
  <h2>Approach</h2>
  <p>
    I combined previous-frame conditioning with explicit consistency objectives. Pixel-transition
    consistency targets abrupt appearance changes, while facial-landmark consistency provides a
    geometric signal tied to facial structure. The model therefore learns from relationships
    across frames as well as from individual images.
  </p>
</section>

<section class="project-section">
  <h2>Evaluation and evidence</h2>
  <p>
    I used video-oriented evaluation and reproducible experiments to examine temporal behavior.
    The publication contains the reported measurements and experimental images; this summary
    does not add results that are not available in the repository.
  </p>
  <div class="evidence-block">
    <strong>Evaluation focus:</strong> plausible frame → incoherent video → temporal failure
    analysis → explicit temporal and geometric constraints → video-oriented evaluation.
  </div>
</section>

<section class="project-section">
  <h2>Technical implementation</h2>
  <p>
    Python and TensorFlow support the generative-adversarial training pipeline, facial-landmark
    processing, video generation, and controlled experiments. Docker makes the research
    environment easier to reproduce and inspect.
  </p>
</section>

<section class="project-section">
  <h2>What I learned</h2>
  <p>
    A property that exists across outputs must be represented in the method and measured at the
    sequence level. Frame-level results alone do not establish temporal coherence.
  </p>
</section>

<div class="project-links">
  <a class="button-link primary" href="https://github.com/lapidarioz/temporal-coherence">Code repository</a>
  <a class="button-link" href="https://doi.org/10.1109/ACCESS.2025.3612820">IEEE Access article</a>
</div>
