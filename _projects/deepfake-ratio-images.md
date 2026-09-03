---
layout: page
title: Deepfake Detection Based on Ratio Images
description: Detecting manipulated videos through interpretable temporal differences between adjacent frames.
importance: 3
featured: true
domain: Synthetic media · Reproducible ML
approach: Adjacent-frame ratio images, engineered face and background features, and video-level Random Forest classification.
card_steps: [Adjacent frames, Temporal features, Video decision]
tech: [Python, OpenCV, scikit-learn, Feature engineering, Video processing]
github: https://github.com/lapidarioz/DeepFakes
paper: https://doi.org/10.1109/IIAIAAI55812.2022.00086
---

<p class="project-intro">
  I investigated temporal differences between adjacent frames as an interpretable signal for
  video-level deepfake detection. This complements methods that inspect only the appearance of
  individual frames.
</p>

<ol class="system-flow" aria-label="Conceptual deepfake-detection pipeline">
  <li>Adjacent video frames</li>
  <li>Face and background regions</li>
  <li>Ratio-image construction</li>
  <li>Engineered temporal features</li>
  <li>Random Forest video classification</li>
</ol>

<section class="project-section">
  <h2>Problem</h2>
  <p>
    A manipulated frame may appear realistic when inspected on its own. Artifacts can instead
    emerge in how facial and background regions change across time, so static inspection may
    discard useful evidence.
  </p>
</section>

<section class="project-section">
  <h2>Why it matters</h2>
  <p>
    Manipulation artifacts can emerge over time rather than within a single frame. Representing
    temporal behavior provides evidence that a frame-based detector may discard.
  </p>
</section>

<section class="project-section">
  <h2>Approach</h2>
  <p>
    I construct ratio images from adjacent frames and extract features from temporal
    changes in face and background regions. A Random Forest combines those engineered signals into
    a video-level classification.
  </p>
</section>

<section class="project-section">
  <h2>Evaluation and evidence</h2>
  <p>
    The repository contains the implementation needed to reproduce the research workflow. The
    publication reports the experimental evaluation; this summary does not add metrics that are
    not available in the repository.
  </p>
  <div class="evidence-block">
    <strong>Core hypothesis:</strong> temporal behavior can expose manipulation artifacts that static appearance may miss.
  </div>
</section>

<section class="project-section">
  <h2>Technical implementation</h2>
  <p>
    Python and OpenCV handle video and region processing; scikit-learn supports feature-based
    classification. The explicit feature pipeline keeps the relationship between temporal artifacts
    and the classifier input inspectable.
  </p>
</section>

<section class="project-section">
  <h2>What I learned</h2>
  <p>
    When a failure develops over time, the evaluation must preserve that temporal context.
    Video-level evidence can reveal behavior that frame-level appearance obscures.
  </p>
</section>

<div class="project-links">
  <a class="button-link primary" href="https://github.com/lapidarioz/DeepFakes">Code repository</a>
  <a class="button-link" href="https://doi.org/10.1109/IIAIAAI55812.2022.00086">Conference paper</a>
</div>
