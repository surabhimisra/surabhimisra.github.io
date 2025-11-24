---
layout: default
title: "Home"
---

<div style="max-width: 900px; margin: 0 auto; padding: 2rem 1.5rem;">

  <!-- SM Logo + Name -->
  <div style="display: flex; align-items: center; gap: 10px; margin: 2rem 0 1.5rem 0;">
    <div style="background: #f2f2f2; padding: 6px 10px; border-radius: 6px; font-weight: 600; font-size: 0.95rem;">
      SM
    </div>
    <div style="font-size: 1.1rem; font-weight: 600;">
      Surabhi Misra
    </div>
  </div>

  <!-- Hero -->
  <section style="margin-bottom: 2.5rem;">
   <h1 style="font-size: 2rem; margin-bottom: 0.4rem;">
      Hi, I am Surabhi.
    </h1>
    <p style="font-size: 1.05rem; line-height: 1.6; max-width: 650px;">
      I am an ASIC Design Engineer working on high speed networking silicon and exploring hardware security,
      especially hardware Trojans, logic locking, and security aware RTL design. I like building small,
      concrete experiments and sharing what I learn with students and early career engineers.
    </p>
  </section>

  <!-- Highlights -->
  <section style="margin-bottom: 2.5rem;">
    <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">What I am working on</h2>
    <ul style="line-height: 1.7; padding-left: 1.2rem;">
      <li>Designing and verifying RTL for networking ASICs.</li>
      <li>Building small, reproducible experiments for hardware Trojan behavior and detection.</li>
      <li>Using NEOS based logic locking on simple ISCAS circuits and observing switching activity.</li>
      <li>Preparing talks and material on chip security for student groups and future conferences.</li>
    </ul>
  </section>

  <!-- Featured Projects -->
  <section style="margin-bottom: 2.5rem;">
    <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">Featured project</h2>

    <div style="border: 1px solid #e1e4e8; border-radius: 8px; padding: 1rem 1.2rem; margin-bottom: 1rem;">
      <h3 style="margin-top: 0; margin-bottom: 0.3rem; font-size: 1.1rem;">
        <a href="https://github.com/surabhimisra/hardware-trojan-detection-experiments" target="_blank">
          Hardware Trojan and Logic Locking Lab Series
        </a>
      </h3>
      <p style="margin: 0.2rem 0 0.5rem 0; font-size: 0.95rem; line-height: 1.5;">
        A hands on repository with baseline RTL designs, Trojan inserted variants, and experiments on rare trigger
        Trojans, sequential triggers, logic locking, and basic switching activity observations. The goal is to give
        students and early engineers simple entry points into chip security.
      </p>
      <p style="margin: 0; font-size: 0.9rem; color: #555;">
        Tech: Verilog, Icarus Verilog, VCD waveforms, Python scripts, NEOS based logic locking.
      </p>
    </div>
  </section>

  <!-- Talks / Speaking -->
 <section style="margin-bottom: 2.5rem;">
  <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">Talks and speaking</h2>

  <p style="font-size: 0.98rem; line-height: 1.6; max-width: 650px;">
    I have presented technical topics in academic, industry, and community settings, including Cisco internal
    presentations, USC course projects, and student events.
  </p>

  <ul style="line-height: 1.7; padding-left: 1.2rem; font-size: 0.96rem;">
    <li>USC SWE guest session on moving from USC to an ASIC role and an introduction to chip security.</li>
    <li>Logic locking and hardware Trojan project presentations during my masters at USC.</li>
    <li>Architecture presentations on NoC and processor design, and other course projects.</li>
    <li>Cisco internship summary and innovation challenge presentations.</li>
  </ul>

  <p style="font-size: 0.95rem; margin-top: 0.8rem;">
    See all talks on the <a href="/talks" style="text-decoration: underline;">Talks page</a>.
  </p>

  <p style="font-size: 0.95rem; margin-top: 0.4rem;">
    Read my GHC 2026 session proposal here:  
    <a href="/ghc2026" style="text-decoration: underline;">GHC 2026 Talk</a>
  </p>
</section>


  <!-- Blog / Writing -->
  <section style="margin-bottom: 2.5rem;">
  <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">Writing</h2>

  <p style="font-size: 0.98rem; line-height: 1.6; max-width: 650px;">
    I write short guides and explanations on hardware security, RTL concepts, and early career engineering topics.
    You can find the full list on the 
    <a href="/writing" style="text-decoration: underline;">Writing page</a>.
  </p>

  <div style="margin-top: 1rem; font-size: 0.98rem; line-height: 1.6; max-width: 650px;">
    <strong>Featured article:</strong><br>
    <a href="/logic-locking-guide" style="text-decoration: underline;">
      A Technical Guide to Logic Locking for Chip Security
    </a>
  </div>

  <ul style="line-height: 1.7; padding-left: 1.2rem; margin-top: 1rem;">
    <li>Short explainers on RTL design and verification.</li>
    <li>Walkthroughs of hardware Trojan experiments from my open source repo.</li>
    <li>Notes on ASIC careers and early engineering growth.</li>
  </ul>

 <p style="font-size: 0.95rem; margin-top: 0.8rem;">
  I also publish on <a href="https://medium.com/@surabhi.misra30" target="_blank" style="text-decoration: underline;">Medium</a> when I write longer posts.
</p>
</section>

<section style="margin-bottom: 2.5rem;">
  <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">Latest posts</h2>

  <ul style="line-height: 1.7; padding-left: 1.2rem;">
    {% for post in site.posts limit:3 %}
      <li>
        <a href="{{ post.url | relative_url }}" style="text-decoration: underline;">
          {{ post.title }}
        </a>
        <span style="font-size: 0.85rem; color: #666;">
          ({{ post.date | date: "%b %-d, %Y" }})
        </span>
      </li>
    {% endfor %}
  </ul>

  <p style="font-size: 0.95rem; margin-top: 0.8rem;">
    See all posts on the <a href="/writing" style="text-decoration: underline;">Writing page</a>.
  </p>
</section>



  <!-- About / Background -->
  <section style="margin-bottom: 2.5rem;">
    <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">About</h2>
    <p style="font-size: 0.98rem; line-height: 1.6; max-width: 700px;">
      I work in ASIC design and verification for networking chips, and I am especially interested in how we can make
      hardware more trustworthy, from RTL all the way to silicon. During my masters at USC I worked on logic locking
      and hardware Trojan concepts as part of my graduate coursework and projects, and I am now turning those ideas
      into small, practical experiments and talks.
    </p>
  </section>

  <!-- Contact -->
  <section style="margin-bottom: 1.5rem;">
    <h2 style="font-size: 1.5rem; margin-bottom: 0.8rem;">Contact</h2>
    <p style="font-size: 0.98rem; line-height: 1.6;">
      The easiest way to reach me is here:
    </p>
    <ul style="line-height: 1.7; padding-left: 1.2rem; font-size: 0.98rem;">
      <li>
        <a href="https://www.linkedin.com/in/surabhi-misra" target="_blank">
          LinkedIn
        </a>
      </li>
      <li>
        <a href="https://github.com/surabhimisra" target="_blank">
          GitHub
        </a>
      </li>
    </ul>
  </section>

</div>
