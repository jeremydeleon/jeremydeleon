<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Jeremy De Leon — Mechanical Engineer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    /* ─── Palette ─── */
    :root {
      --cream:       #F5F0E8;
      --warm-white:  #FDFAF4;
      --terracotta:  #C4603A;
      --terra-light: #E8C4B0;
      --terra-muted: #F0DDD3;
      --sage:        #6B8C72;
      --sage-light:  #C2D4C4;
      --sage-muted:  #DDE9DE;
      --gold:        #B8883A;
      --gold-light:  #E8D4A8;
      --gold-muted:  #F2E8D0;
      --ink:         #2A2520;
      --ink-mid:     #5C5248;
      --ink-soft:    #8C8078;
      --border:      rgba(42,37,32,0.12);
      --border-mid:  rgba(42,37,32,0.2);
    }

    /* ─── Reset & Base ─── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--ink);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* Grain texture overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
    }

    /* ─── Typography ─── */
    h1, h2, h3, h4 {
      font-family: 'DM Serif Display', serif;
      font-weight: 400;
      line-height: 1.2;
    }

    .label {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--ink-soft);
    }

    /* ─── Nav ─── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.25rem 3rem;
      background: rgba(245,240,232,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: 'DM Serif Display', serif;
      font-size: 1.1rem;
      color: var(--ink);
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 13px;
      font-weight: 400;
      color: var(--ink-mid);
      text-decoration: none;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--terracotta); }

    /* ─── Layout Utilities ─── */
    section {
      position: relative;
      z-index: 1;
      padding: 6rem 3rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 1rem;
      margin-bottom: 3.5rem;
    }

    .section-header h2 { font-size: clamp(2rem, 4vw, 2.75rem); }

    .section-line {
      flex: 1;
      height: 1px;
      background: var(--border-mid);
    }

    /* ─── Hero ─── */
    #hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding-top: 8rem;
      padding-bottom: 4rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    .hero-eyebrow {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      margin-bottom: 1.5rem;
    }

    .hero-eyebrow-dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      background: var(--terracotta);
      animation: pulse 2.5s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); opacity: 1; }
      50% { transform: scale(1.4); opacity: 0.6; }
    }

    .hero-name {
      font-size: clamp(3.5rem, 8vw, 6.5rem);
      color: var(--ink);
      line-height: 1.05;
      margin-bottom: 0.5rem;
    }

    .hero-name em {
      font-style: italic;
      color: var(--terracotta);
    }

    .hero-tagline {
      font-size: clamp(1.1rem, 2vw, 1.4rem);
      color: var(--ink-mid);
      font-weight: 300;
      margin-bottom: 2.5rem;
      max-width: 520px;
    }

    .hero-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-bottom: 3rem;
    }

    .pill {
      padding: 0.4rem 1rem;
      border-radius: 100px;
      font-size: 13px;
      font-weight: 400;
      border: 1px solid;
    }

    .pill-terra {
      background: var(--terra-muted);
      border-color: var(--terra-light);
      color: var(--terracotta);
    }

    .pill-sage {
      background: var(--sage-muted);
      border-color: var(--sage-light);
      color: var(--sage);
    }

    .pill-gold {
      background: var(--gold-muted);
      border-color: var(--gold-light);
      color: var(--gold);
    }

    .hero-cta {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.75rem 1.75rem;
      border-radius: 6px;
      font-size: 14px;
      font-weight: 500;
      font-family: 'DM Sans', sans-serif;
      cursor: pointer;
      text-decoration: none;
      transition: all 0.2s;
      border: 1.5px solid;
    }

    .btn-primary {
      background: var(--terracotta);
      border-color: var(--terracotta);
      color: #fff;
    }

    .btn-primary:hover {
      background: #b05530;
      border-color: #b05530;
      transform: translateY(-1px);
    }

    .btn-outline {
      background: transparent;
      border-color: var(--border-mid);
      color: var(--ink);
    }

    .btn-outline:hover {
      border-color: var(--ink-mid);
      transform: translateY(-1px);
    }

    .hero-scroll {
      position: absolute;
      bottom: 2.5rem;
      left: 3rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      color: var(--ink-soft);
      font-size: 12px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .scroll-line {
      width: 40px;
      height: 1px;
      background: var(--ink-soft);
      animation: scrollLine 2s ease-in-out infinite;
    }

    @keyframes scrollLine {
      0%, 100% { width: 40px; opacity: 1; }
      50% { width: 20px; opacity: 0.4; }
    }

    /* ─── Decorative Background Text ─── */
    .bg-text {
      position: absolute;
      font-family: 'DM Serif Display', serif;
      font-size: clamp(6rem, 16vw, 14rem);
      color: rgba(42,37,32,0.04);
      pointer-events: none;
      white-space: nowrap;
      line-height: 1;
      z-index: 0;
    }

    /* ─── About ─── */
    #about { background: transparent; }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .about-text p {
      color: var(--ink-mid);
      margin-bottom: 1.25rem;
      font-size: 1.05rem;
    }

    .about-text p:last-child { margin-bottom: 0; }

    .about-details {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .detail-card {
      background: var(--warm-white);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 1.25rem 1.5rem;
      transition: border-color 0.2s, transform 0.2s;
    }

    .detail-card:hover {
      border-color: var(--border-mid);
      transform: translateX(4px);
    }

    .detail-card-label {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--ink-soft);
      margin-bottom: 0.3rem;
    }

    .detail-card-value {
      font-size: 1rem;
      font-weight: 400;
      color: var(--ink);
    }

    .detail-card-accent { border-left: 3px solid var(--terracotta); }
    .detail-card-sage   { border-left: 3px solid var(--sage); }
    .detail-card-gold   { border-left: 3px solid var(--gold); }

    /* ─── Skills ─── */
    #skills {
      background: var(--warm-white);
      max-width: 100%;
      padding: 6rem 0;
    }

    #skills .inner {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 3rem;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1.5rem;
    }

    .skill-category {
      background: var(--cream);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 1.75rem;
      transition: transform 0.2s, border-color 0.2s;
    }

    .skill-category:hover {
      transform: translateY(-3px);
      border-color: var(--border-mid);
    }

    .skill-category-icon {
      font-size: 1.75rem;
      margin-bottom: 1rem;
    }

    .skill-category h3 {
      font-size: 1.1rem;
      margin-bottom: 1rem;
      color: var(--ink);
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
    }

    .skill-tag {
      font-size: 12px;
      padding: 0.25rem 0.6rem;
      border-radius: 4px;
      background: var(--warm-white);
      border: 1px solid var(--border);
      color: var(--ink-mid);
    }

    /* ─── Projects ─── */
    #projects { position: relative; }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 1.75rem;
    }

    .project-card {
      background: var(--warm-white);
      border: 1px solid var(--border);
      border-radius: 16px;
      overflow: hidden;
      transition: transform 0.25s, box-shadow 0.25s, border-color 0.25s;
    }

    .project-card:hover {
      transform: translateY(-5px);
      border-color: var(--border-mid);
      box-shadow: 0 16px 40px rgba(42,37,32,0.08);
    }

    .project-card-header {
      height: 180px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3.5rem;
      position: relative;
      overflow: hidden;
    }

    .project-card-header::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to bottom, transparent 40%, rgba(253,250,244,0.9) 100%);
    }

    .header-terra { background: var(--terra-muted); }
    .header-sage  { background: var(--sage-muted); }
    .header-gold  { background: var(--gold-muted); }
    .header-blue  { background: #dde8f0; }
    .header-pink  { background: #f0dde8; }

    .project-card-body {
      padding: 1.5rem;
    }

    .project-meta {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 0.75rem;
    }

    .project-tag {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 0.2rem 0.6rem;
      border-radius: 4px;
    }

    .tag-terra { background: var(--terra-muted); color: var(--terracotta); }
    .tag-sage  { background: var(--sage-muted); color: var(--sage); }
    .tag-gold  { background: var(--gold-muted); color: var(--gold); }

    .project-year {
      font-size: 12px;
      color: var(--ink-soft);
    }

    .project-card h3 {
      font-size: 1.3rem;
      margin-bottom: 0.6rem;
    }

    .project-card p {
      font-size: 14px;
      color: var(--ink-mid);
      line-height: 1.65;
      margin-bottom: 1.25rem;
    }

    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 0.35rem;
      margin-bottom: 1.25rem;
    }

    .tech-chip {
      font-size: 11px;
      padding: 0.2rem 0.55rem;
      border-radius: 3px;
      background: var(--cream);
      border: 1px solid var(--border);
      color: var(--ink-soft);
    }

    .project-links {
      display: flex;
      gap: 0.6rem;
    }

    .project-link {
      font-size: 13px;
      color: var(--ink-mid);
      text-decoration: none;
      padding: 0.3rem 0.75rem;
      border: 1px solid var(--border-mid);
      border-radius: 5px;
      transition: all 0.2s;
    }

    .project-link:hover {
      color: var(--terracotta);
      border-color: var(--terracotta);
    }

    /* ─── Experience / Timeline ─── */
    #experience { background: transparent; }

    .timeline {
      position: relative;
      padding-left: 2.5rem;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 0; top: 0.5rem; bottom: 0;
      width: 1px;
      background: var(--border-mid);
    }

    .timeline-item {
      position: relative;
      margin-bottom: 3rem;
    }

    .timeline-item:last-child { margin-bottom: 0; }

    .timeline-dot {
      position: absolute;
      left: -2.5rem;
      top: 0.35rem;
      width: 11px; height: 11px;
      border-radius: 50%;
      border: 2px solid var(--terracotta);
      background: var(--cream);
      transform: translateX(-5px);
    }

    .timeline-date {
      font-size: 12px;
      color: var(--ink-soft);
      letter-spacing: 0.08em;
      margin-bottom: 0.35rem;
    }

    .timeline-item h3 {
      font-size: 1.25rem;
      margin-bottom: 0.15rem;
    }

    .timeline-org {
      font-size: 14px;
      color: var(--terracotta);
      margin-bottom: 0.75rem;
    }

    .timeline-item p {
      font-size: 14px;
      color: var(--ink-mid);
      max-width: 580px;
    }

    /* ─── Contact ─── */
    #contact {
      background: var(--ink);
      max-width: 100%;
      padding: 6rem 0;
      color: var(--cream);
    }

    #contact .inner {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 3rem;
    }

    #contact .section-header h2 { color: var(--cream); }
    #contact .section-line { background: rgba(245,240,232,0.2); }
    #contact .label { color: rgba(245,240,232,0.4); }

    .contact-grid {
      display: grid;
      grid-template-columns: 1.4fr 1fr;
      gap: 5rem;
      align-items: start;
    }

    .contact-intro {
      font-size: 1.5rem;
      font-family: 'DM Serif Display', serif;
      line-height: 1.45;
      color: var(--cream);
      margin-bottom: 2rem;
    }

    .contact-intro em {
      font-style: italic;
      color: var(--terra-light);
    }

    .contact-links {
      display: flex;
      flex-direction: column;
      gap: 0.9rem;
    }

    .contact-link-item {
      display: flex;
      align-items: center;
      gap: 1rem;
      color: rgba(245,240,232,0.7);
      text-decoration: none;
      font-size: 14px;
      transition: color 0.2s;
      padding-bottom: 0.9rem;
      border-bottom: 1px solid rgba(245,240,232,0.1);
    }

    .contact-link-item:hover { color: var(--terra-light); }
    .contact-link-item:last-child { border-bottom: none; }

    .contact-icon {
      width: 36px; height: 36px;
      border-radius: 8px;
      background: rgba(245,240,232,0.08);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
      flex-shrink: 0;
    }

    /* ─── Footer ─── */
    footer {
      background: var(--ink);
      border-top: 1px solid rgba(245,240,232,0.1);
      text-align: center;
      padding: 1.5rem 3rem;
      font-size: 12px;
      color: rgba(245,240,232,0.3);
    }

    /* ─── Fade-in animations ─── */
    .fade-up {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    .fade-up.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ─── Responsive ─── */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { gap: 1.25rem; }
      section { padding: 4rem 1.5rem; }
      #hero { padding: 7rem 1.5rem 4rem; }
      .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
      .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
      #skills .inner, #contact .inner { padding: 0 1.5rem; }
      .hero-scroll { left: 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- ─── Navigation ─── -->
  <nav>
    <a href="#hero" class="nav-logo">JDL</a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- ─── Hero ─── -->
  <div style="position:relative; overflow:hidden;">
    <div class="bg-text" style="right:-2%; top:30%;">ME</div>
    <section id="hero">
      <div class="hero-eyebrow">
        <div class="hero-eyebrow-dot"></div>
        <span class="label">Available for internships & research</span>
      </div>
      <h1 class="hero-name">
        Jeremy<br><em>De Leon</em>
      </h1>
      <p class="hero-tagline">
        Mechanical Engineering student at UCLA — designing systems that bridge physical precision with thoughtful problem-solving.
      </p>
      <div class="hero-pills">
        <span class="pill pill-terra">🎓 UCLA</span>
        <span class="pill pill-sage">⚙️ Mechanical Engineering</span>
        <span class="pill pill-gold">📍 Los Angeles, CA</span>
      </div>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View My Work</a>
        <a href="#contact" class="btn btn-outline">Get in Touch</a>
        <a href="resume.pdf" class="btn btn-outline" target="_blank">Resume ↗</a>
      </div>
      <div class="hero-scroll">
        <div class="scroll-line"></div>
        Scroll
      </div>
    </section>
  </div>

  <!-- ─── About ─── -->
  <section id="about">
    <div class="section-header fade-up">
      <h2>About</h2>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="about-text fade-up">
        <p>
          I'm Jeremy, a mechanical engineering student at UCLA with a passion for turning complex problems into elegant, functional solutions. Whether it's modeling fluid dynamics, prototyping hardware, or running FEA simulations, I love the entire process — from napkin sketch to finished component.
        </p>
        <p>
          Outside the lab, I'm drawn to how engineering intersects with sustainability and design. I believe the best engineering is invisible — it just works, beautifully.
        </p>
        <p>
          I'm actively looking for internship opportunities in product development, aerospace, robotics, or sustainable energy to grow my hands-on experience alongside my coursework.
        </p>
      </div>
      <div class="about-details fade-up">
        <div class="detail-card detail-card-accent">
          <div class="detail-card-label">University</div>
          <div class="detail-card-value">University of California, Los Angeles</div>
        </div>
        <div class="detail-card detail-card-sage">
          <div class="detail-card-label">Major</div>
          <div class="detail-card-value">Mechanical Engineering, B.S.</div>
        </div>
        <div class="detail-card detail-card-gold">
          <div class="detail-card-label">Interests</div>
          <div class="detail-card-value">Robotics · Sustainable Design · Aerospace</div>
        </div>
        <div class="detail-card detail-card-accent">
          <div class="detail-card-label">Status</div>
          <div class="detail-card-value">Open to Internships — Summer 2025</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ─── Skills ─── -->
  <div id="skills">
    <div class="inner">
      <div class="section-header fade-up">
        <h2>Skills</h2>
        <div class="section-line"></div>
      </div>
      <div class="skills-grid">
        <div class="skill-category fade-up">
          <div class="skill-category-icon">🔩</div>
          <h3>CAD & Modeling</h3>
          <div class="skill-tags">
            <span class="skill-tag">SolidWorks</span>
            <span class="skill-tag">AutoCAD</span>
            <span class="skill-tag">Fusion 360</span>
            <span class="skill-tag">CATIA</span>
            <span class="skill-tag">Onshape</span>
          </div>
        </div>
        <div class="skill-category fade-up">
          <div class="skill-category-icon">🧮</div>
          <h3>Analysis & Simulation</h3>
          <div class="skill-tags">
            <span class="skill-tag">ANSYS</span>
            <span class="skill-tag">FEA</span>
            <span class="skill-tag">CFD</span>
            <span class="skill-tag">MATLAB</span>
            <span class="skill-tag">Simulink</span>
          </div>
        </div>
        <div class="skill-category fade-up">
          <div class="skill-category-icon">🖨️</div>
          <h3>Fabrication</h3>
          <div class="skill-tags">
            <span class="skill-tag">3D Printing</span>
            <span class="skill-tag">CNC Machining</span>
            <span class="skill-tag">Laser Cutting</span>
            <span class="skill-tag">Welding</span>
            <span class="skill-tag">GD&T</span>
          </div>
        </div>
        <div class="skill-category fade-up">
          <div class="skill-category-icon">💻</div>
          <h3>Programming</h3>
          <div class="skill-tags">
            <span class="skill-tag">Python</span>
            <span class="skill-tag">MATLAB</span>
            <span class="skill-tag">C++</span>
            <span class="skill-tag">Arduino</span>
            <span class="skill-tag">R</span>
          </div>
        </div>
        <div class="skill-category fade-up">
          <div class="skill-category-icon">📐</div>
          <h3>Engineering Fundamentals</h3>
          <div class="skill-tags">
            <span class="skill-tag">Thermodynamics</span>
            <span class="skill-tag">Fluid Mechanics</span>
            <span class="skill-tag">Statics</span>
            <span class="skill-tag">Dynamics</span>
            <span class="skill-tag">Materials Science</span>
          </div>
        </div>
        <div class="skill-category fade-up">
          <div class="skill-category-icon">🤝</div>
          <h3>Collaboration</h3>
          <div class="skill-tags">
            <span class="skill-tag">Technical Writing</span>
            <span class="skill-tag">LaTeX</span>
            <span class="skill-tag">Git</span>
            <span class="skill-tag">Agile / Scrum</span>
            <span class="skill-tag">Notion</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ─── Projects ─── -->
  <section id="projects" style="position:relative; overflow:hidden;">
    <div class="bg-text" style="left:-2%; bottom:-10%; font-size: clamp(5rem, 12vw, 11rem);">work</div>
    <div class="section-header fade-up">
      <h2>Projects</h2>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <div class="project-card fade-up">
        <div class="project-card-header header-terra">⚙️</div>
        <div class="project-card-body">
          <div class="project-meta">
            <span class="project-tag tag-terra">Design</span>
            <span class="project-year">2024</span>
          </div>
          <h3>Lightweight Drone Frame</h3>
          <p>Designed and FEA-tested a carbon fiber drone frame optimized for weight reduction while maintaining structural integrity under 3G load conditions. Achieved 22% weight reduction vs. baseline aluminum design.</p>
          <div class="project-tech">
            <span class="tech-chip">SolidWorks</span>
            <span class="tech-chip">ANSYS</span>
            <span class="tech-chip">Carbon Fiber</span>
            <span class="tech-chip">FEA</span>
          </div>
          <div class="project-links">
            <a href="#" class="project-link">GitHub ↗</a>
            <a href="#" class="project-link">Report ↗</a>
          </div>
        </div>
      </div>

      <div class="project-card fade-up">
        <div class="project-card-header header-sage">🌊</div>
        <div class="project-card-body">
          <div class="project-meta">
            <span class="project-tag tag-sage">Simulation</span>
            <span class="project-year">2024</span>
          </div>
          <h3>Pipe Flow CFD Study</h3>
          <p>Conducted a comparative CFD analysis of turbulent pipe flow across different Reynolds numbers, validating simulation outputs against Moody chart correlations. Results within 4% of experimental benchmarks.</p>
          <div class="project-tech">
            <span class="tech-chip">MATLAB</span>
            <span class="tech-chip">CFD</span>
            <span class="tech-chip">Fluid Mechanics</span>
          </div>
          <div class="project-links">
            <a href="#" class="project-link">GitHub ↗</a>
            <a href="#" class="project-link">Slides ↗</a>
          </div>
        </div>
      </div>

      <div class="project-card fade-up">
        <div class="project-card-header header-gold">🤖</div>
        <div class="project-card-body">
          <div class="project-meta">
            <span class="project-tag tag-gold">Robotics</span>
            <span class="project-year">2023</span>
          </div>
          <h3>Autonomous Line-Following Robot</h3>
          <p>Built and programmed a sensor-guided robot using a PID control loop for precision line tracking. Won second place at UCLA's introductory robotics competition.</p>
          <div class="project-tech">
            <span class="tech-chip">Arduino</span>
            <span class="tech-chip">C++</span>
            <span class="tech-chip">PID Control</span>
            <span class="tech-chip">3D Printing</span>
          </div>
          <div class="project-links">
            <a href="#" class="project-link">GitHub ↗</a>
            <a href="#" class="project-link">Demo ↗</a>
          </div>
        </div>
      </div>

      <div class="project-card fade-up">
        <div class="project-card-header header-blue">♻️</div>
        <div class="project-card-body">
          <div class="project-meta">
            <span class="project-tag tag-sage">Sustainability</span>
            <span class="project-year">2023</span>
          </div>
          <h3>Passive Solar Water Heater</h3>
          <p>Designed a low-cost passive solar water heating system for residential use. Modeled thermal performance with thermodynamic equations and validated with prototype testing, achieving ~65% efficiency gain.</p>
          <div class="project-tech">
            <span class="tech-chip">Thermodynamics</span>
            <span class="tech-chip">Fusion 360</span>
            <span class="tech-chip">Python</span>
          </div>
          <div class="project-links">
            <a href="#" class="project-link">GitHub ↗</a>
          </div>
        </div>
      </div>

    </div>
  </section>

  <!-- ─── Experience / Timeline ─── -->
  <section id="experience">
    <div class="section-header fade-up">
      <h2>Experience</h2>
      <div class="section-line"></div>
    </div>
    <div style="display:grid; grid-template-columns: 1fr 1fr; gap: 0 5rem;">
      <div>
        <p class="label" style="margin-bottom: 2rem;">Work & Research</p>
        <div class="timeline">
          <div class="timeline-item fade-up">
            <div class="timeline-dot"></div>
            <div class="timeline-date">June 2024 – Present</div>
            <h3>Undergraduate Researcher</h3>
            <div class="timeline-org">UCLA MAE Department</div>
            <p>Assisting graduate researchers in experimental mechanics lab. Running tensile tests, analyzing material stress-strain data, and contributing to published documentation.</p>
          </div>
          <div class="timeline-item fade-up">
            <div class="timeline-dot"></div>
            <div class="timeline-date">Summer 2023</div>
            <h3>Engineering Intern</h3>
            <div class="timeline-org">Local Manufacturing Firm</div>
            <p>Shadowed senior engineers on production floor, assisted with quality control checks, and created updated GD&T drawings for two product lines using AutoCAD.</p>
          </div>
        </div>
      </div>
      <div>
        <p class="label" style="margin-bottom: 2rem;">Leadership & Clubs</p>
        <div class="timeline">
          <div class="timeline-item fade-up">
            <div class="timeline-dot" style="border-color: var(--sage);"></div>
            <div class="timeline-date">2023 – Present</div>
            <h3>Technical Lead</h3>
            <div class="timeline-org" style="color: var(--sage);">UCLA Bruin Racing</div>
            <p>Leading the suspension subteam for UCLA's FSAE competition vehicle. Responsible for geometry modeling, component selection, and track testing analysis.</p>
          </div>
          <div class="timeline-item fade-up">
            <div class="timeline-dot" style="border-color: var(--gold);"></div>
            <div class="timeline-date">2022 – 2023</div>
            <h3>Member</h3>
            <div class="timeline-org" style="color: var(--gold);">Society of Women Engineers (Ally)</div>
            <p>Participated in outreach events and mentorship programs supporting underrepresented students in STEM at the K–12 level.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ─── Contact ─── -->
  <div id="contact">
    <div class="inner">
      <div class="section-header fade-up">
        <h2>Contact</h2>
        <div class="section-line"></div>
      </div>
      <div class="contact-grid">
        <div class="fade-up">
          <p class="contact-intro">
            Let's build something that <em>matters</em>. Whether it's a project, an internship, or just a conversation — I'd love to connect.
          </p>
          <a href="mailto:jeremy@example.com" class="btn btn-primary">Say Hello →</a>
        </div>
        <div class="contact-links fade-up">
          <a href="mailto:jeremy@example.com" class="contact-link-item">
            <div class="contact-icon">✉️</div>
            jeremy@example.com
          </a>
          <a href="https://linkedin.com/in/jeremydeleon" target="_blank" class="contact-link-item">
            <div class="contact-icon">in</div>
            linkedin.com/in/jeremydeleon
          </a>
          <a href="https://github.com/jeremydeleon" target="_blank" class="contact-link-item">
            <div class="contact-icon">⌥</div>
            github.com/jeremydeleon
          </a>
          <a href="resume.pdf" target="_blank" class="contact-link-item">
            <div class="contact-icon">↓</div>
            Download Resume (PDF)
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- ─── Footer ─── -->
  <footer>
    © 2025 Jeremy De Leon · Built with HTML & hosted on GitHub Pages
  </footer>

  <!-- ─── Scroll Animation ─── -->
  <script>
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          setTimeout(() => {
            entry.target.classList.add('visible');
          }, i * 80);
        }
      });
    }, { threshold: 0.12 });

    document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));
  </script>

</body>
</html>
