<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Smit Kohale - GitHub Profile</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #0a0a0f;
      --bg-secondary: #12121f;
      --fg: #e8e8f0;
      --muted: #6b6b80;
      --accent: #00d4aa;
      --accent-glow: rgba(0, 212, 170, 0.4);
      --card: #1a1a24;
      --border: #2a2a3a;
      --success: #00e676;
      --warning: #ff6b35;
      --error: #ff4757;
    }

    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg);
      color: var(--fg);
      margin: 0;
      padding: 0;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }

    /* Animated Background */
    .bg-pattern {
      position: fixed;
      inset: 0;
      background: 
        radial-gradient(ellipse 80% 50% at 20% 20%, rgba(0, 212, 170, 0.15) 0%, transparent 50%),
        radial-gradient(ellipse 60% 40% at 80% 80%, rgba(0, 100, 200, 0.1) 0%, transparent 50%),
        var(--bg);
      z-index: -2;
    }

    .grid-overlay {
      position: fixed;
      inset: 0;
      background-image: 
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      opacity: 0.15;
      z-index: -1;
      animation: gridMove 20s linear infinite;
    }

    @keyframes gridMove {
      0% { transform: translate(0, 0); }
      100% { transform: translate(60px, 60px); }
    }

    .noise {
      position: fixed;
      inset: 0;
      pointer-events: none;
      opacity: 0.03;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
      z-index: -1;
    }

    /* Header Section */
    .header {
      text-align: center;
      padding: 100px 20px 40px;
      animation: fadeSlideUp 1s ease-out;
    }

    @keyframes fadeSlideUp {
      from {
        opacity: 0;
        transform: translateY(40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .name {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(2.5rem, 8vw, 4rem);
      font-weight: 700;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--fg) 0%, var(--muted) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 8px;
    }

    .tagline {
      font-size: clamp(1rem, 2.5vw, 1.2rem);
      color: var(--muted);
      margin-bottom: 24px;
    }

    .contact-info {
      display: flex;
      justify-content: center;
      gap: 24px;
      flex-wrap: wrap;
    }

    .contact-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 24px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 30px;
      color: var(--fg);
      text-decoration: none;
      font-size: 0.875rem;
      transition: all 0.3s ease;
      white-space: nowrap;
    }

    .contact-link:hover {
      background: var(--accent);
      color: var(--bg);
      transform: translateY(-2px);
      box-shadow: 0 8px 30px var(--accent-glow);
    }

    .contact-link:hover svg {
      stroke: var(--bg);
    }

    /* Stats Section */
    .stats {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 20px;
      padding: 40px 0;
      animation: fadeSlideUp 1s ease-out 0.2s both;
    }

    .stat-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 24px;
      text-align: center;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .stat-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--accent), transparent, var(--accent));
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .stat-card:hover {
      border-color: var(--accent);
      transform: translateY(-4px);
      box-shadow: 0 12px 30px var(--accent-glow);
    }

    .stat-card:hover::before {
      opacity: 1;
    }

    .stat-icon {
      width: 48px;
      height: 48px;
      margin: 0 auto 16px;
      background: linear-gradient(135deg, var(--accent), #0088aa);
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      color: var(--bg);
      transition: transform 0.3s ease;
    }

    .stat-card:hover .stat-icon {
      transform: scale(1.1);
    }

    .stat-number {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 2.2rem;
      font-weight: 600;
      color: var(--accent);
      margin-bottom: 4px;
    }

    .stat-label {
      font-size: 0.75rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.1em;
    }

    /* Skills Section */
    .skills {
      padding: 40px 0;
      animation: fadeSlideUp 1s ease-out 0.4s both;
    }

    .section-title {
      font-size: 1.5rem;
      font-weight: 600;
      margin-bottom: 24px;
      display: flex;
      align-items: center;
      gap: 8px;
      color: var(--fg);
    }

    .section-title::before {
      content: '';
      width: 4px;
      height: 20px;
      background: var(--accent);
      border-radius: 2px;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 12px;
    }

    .skill-badge {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 10px 16px;
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--fg);
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .skill-badge:hover {
      border-color: var(--accent);
      background: linear-gradient(135deg, var(--accent), #0088aa);
      color: var(--bg);
    }

    .skill-badge i {
      font-size: 0.7rem;
    }

    /* Projects Section */
    .projects {
      padding: 40px 0;
      animation: fadeSlideUp 1s ease-out 0.6s both;
    }

    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 24px;
      margin-bottom: 20px;
      transition: all 0.3s ease;
      opacity: 0;
      transform: translateY(20px);
    }

    .project-card.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .project-card:hover {
      border-color: var(--accent);
      transform: translateY(-4px);
      box-shadow: 0 8px 25px var(--accent-glow);
    }

    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 12px;
    }

    .tech-tag {
      background: var(--bg-secondary);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 4px 12px;
      font-size: 0.7rem;
      font-weight: 500;
      color: var(--muted);
      white-space: nowrap;
      transition: all 0.3s ease;
    }

    .project-card:hover .tech-tag {
      background: var(--accent);
      color: var(--bg);
      border-color: var(--accent);
    }

    /* Experience Section */
    .experience {
      padding: 40px 0;
      animation: fadeSlideUp 1s ease-out 0.8s both;
    }

    .timeline {
      position: relative;
      padding-left: 30px;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 8px;
      top: 0;
      bottom: 0;
      width: 2px;
      background: linear-gradient(var(--accent), var(--fg));
    }

    .experience-item {
      margin-bottom: 30px;
      padding-bottom: 20px;
      border-bottom: 1px solid var(--border);
      position: relative;
    }

    .experience-item:last-child {
      border-bottom: none;
      padding-bottom: 0;
    }

    .experience-date {
      font-size: 0.75rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      margin-bottom: 4px;
    }

    .experience-company {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.1rem;
      font-weight: 600;
      color: var(--accent);
      margin-bottom: 4px;
    }

    .experience-location {
      font-size: 0.8rem;
      color: var(--muted);
      margin-bottom: 12px;
    }

    .experience-bullets {
      list-style: none;
      padding: 0;
    }

    .experience-bullets li {
      padding: 8px 0;
      border-bottom: 1px dashed var(--border);
      font-size: 0.875rem;
      transition: color 0.3s ease;
    }

    .experience-bullets li:hover {
      color: var(--accent);
    }

    .experience-bullets li:last-child {
      border-bottom: none;
    }

    /* Interests/Social */
    .social {
      padding: 40px 0;
      animation: fadeSlideUp 1s ease-out 1s both;
      text-align: center;
    }

    .social-links {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-top: 20px;
    }

    .social-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 12px 24px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 30px;
      color: var(--fg);
      text-decoration: none;
      font-size: 0.875rem;
      transition: all 0.3s ease;
    }

    .social-link:hover {
      background: var(--accent);
      color: var(--bg);
      transform: translateY(-2px);
      box-shadow: 0 8px 30px var(--accent-glow);
    }

    /* Scroll Reveal Animation */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* Reduced Motion */
    @media (prefers-reduced-motion: reduce) {
      .reveal {
        opacity: 1;
        transform: none;
        transition: none;
      }
      .grid-overlay {
        animation: none;
      }
    }
  </style>
</head>
<body>
  <div class="bg-pattern"></div>
  <div class="grid-overlay"></div>
  <div class="noise"></div>

  <div class="container">
    <!-- Header -->
    <header class="header">
      <h1 class="name">Smit Vijay Kohale</h1>
      <p class="tagline">Computer Science Graduate | Data Analyst | Python Enthusiast</p>
      
      <div class="contact-info">
        <a href="mailto:smit.v.kohale@gmail.com" class="contact-link">
          <svg width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
            <path d="M4 0h8a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V2a2 2 0 0 1 2-2zM2 2a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h8a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2H2z"/>
            <path d="M9.5 3.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5zM2 8.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5zm8 0a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5z"/>
          </svg>
          smit.v.kohale@gmail.com
        </a>
        <a href="https://www.linkedin.com/in/smit-kohale/" class="contact-link">
          <svg width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
            <path d="M0 1.1C0 .5.5 0 .5.5S1 0 1.1.1L.14.53C-.26 1.08-.26 2.58.74 4.92l2.97-1.16a3 3 0 0 1 1.96-.52l2.6 2.22c.52.76 1.27.76 1.79 0l2.58-2.18c.98-.37 1.04-1.86.1-2.65l-2.95-1.16a4 4 0 0 0-1.89-1.15l-2.65-2.33a6 6 0 0 1 1.05-3.95l2.58-.96c.53-.2 1.26-.16 1.81.12l2.74 2.18a5.5 5.5 0 0 0 1.18 3.1l2.85-1.15c.74-.3 1.09-1.48.87-2.33L9.9 2.88a3.5 3.5 0 0 0-1.53-2.03l-3.47.99a1 1 0 0 0-.67.49l-3.5 3.98a.5.5 0 0 0 .33.82l3.93-1.45a4.5 4.5 0 0 0 1.17-3.12l-2.66-2.35a6 6 0 0 1-.1-4.08l-2.86.95c-.8.3-1.11 1.4-.93 2.29l2.1 2.88a5.5 5.5 0 0 0-.07 3.17l2.96 1.16a4.5 4.5 0 0 0 1.85 1.53l2.68-.95c.52-.19 1.01-.16 1.33.08l2.9 2.23a3 3 0 0 0 .6 1.81l2.86-1.15c.44-.8.08-1.71-.7-2.17L8.26.58C7.05.15 5.5.05 4.5.15 3.7.26 3.1 1.08 2.19 2.66l.74 1.98a.5.5 0 0 0 .68.46l3.48-.95a3 3 0 0 0 .07-2.08L0 1.1zM12 1.1C11.5 0 11 .1 11.1.2l.14.53c.52 1.52.52 3.02 0 4.54L13.06 9.5a3.5 3.5 0 0 0 .17 2.03l-.45.18c-.52.8-1.18.96-1.83.62L10.4 7.07l-.97-2.28c-.54-.18-1.03-.38-1.4-.62L8.5 4.95l-.76 2.26c-.22.66-.68.75-1.15.35L5.4 6.58 4.4 8.93l.96 2.26c.45.5.98.75 1.5.68l2.31-.87a3.5 3.5 0 0 0 1.05-2.03l-.48-.18c-.32-.67-.87-.88-1.33-.35L3.8 6.58L2.8 4.95l.73 2.26c.2.65.55.74 1.02.38l2.57-1.05a6 6 0 0 1 .1-3.95l-2.58-.96c-.53-.2-1.26-.16-1.81.12L.46 5.28a4.5 4.5 0 0 0-.1 4.08l2.86-.95c.73.3 1.04 1.3.87 2.18l-2.58 1.15a1 1 0 0 0-.67.48l-3.5-3.98a.5.5 0 0 0-.33-.82l-3.93 1.45a4.5 4.5 0 0 0-1.17 3.12l2.66 2.35a6 6 0 0 1 .1 4.08l2.86-.95c.8-.3 1.11-1.4.93-2.29l-2.1-2.88a5.5 5.5 0 0 0 .07-3.17l-2.96-1.16a4.5 4.5 0 0 0-1.85-1.53l-2.68.95c-.52.19-1.01.16-1.33-.08l-2.9-2.23a3 3 0 0 0-.6-1.81l-2.86 1.15c-.44.8-.08 1.71.7 2.17l2.86.95c.44.8 1.11 1.4 1.33.35l2.1 2.88a5.5 5.5 0 0 0 .07 3.17l-2.96-1.16a4.5 4.5 0 0 0-1.85-1.53l-2.68.95c-.52.19-1.01.16-1.33-.08L12 1.1z"/>
          </svg>
          LinkedIn
        </a>
        <a href="https://github.com/smitkohale" class="contact-link">
          <svg width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
            <path d="M8 0C3.6 0 0 3.6 0 8c0 3.5 1.8 6.7 4.9 8.9L15.1 1.5C13.6.3 12.4.1 11.3.1C6.4.1 2.1 4.2 2.1 8c0 3.6 2.6 6.6 5.9 7.6L8 15.6l-2.7 1C5.5 16.9 8 15.3 8 13c0-2.7 1.1-5.2 2.9-6.8zM1.5 8l3.2 1.8.8-3.5H3.7l.8 3.5L1.5 8z"/>
          </svg>
          GitHub
        </a>
      </div>
    </header>

    <!-- Stats -->
    <section class="stats">
      <div class="stat-card reveal">
        <div class="stat-icon"><i>📊</i></div>
        <div class="stat-number" data-target="12">0</div>
        <div class="stat-label">Projects</div>
      </div>
      <div class="stat-card reveal">
        <div class="stat-icon"><i>💼</i></div>
        <div class="stat-number" data-target="2">0</div>
        <div class="stat-label">Internships</div>
      </div>
      <div class="stat-card reveal">
        <div class="stat-icon"><i>🛠️</i></div>
        <div class="stat-number" data-target="15">0</div>
        <div class="stat-label">Skills</div>
      </div>
      <div class="stat-card reveal">
        <div class="stat-icon"><i>🌍</i></div>
        <div class="stat-number" data-target="Nagpur">0</div>
        <div class="stat-label">Location</div>
      </div>
    </section>

    <!-- Skills -->
    <section class="skills">
      <h2 class="section-title">Technical Skills</h2>
      <div class="skills-grid">
        <div><span class="skill-badge"><i class="icon">PY</i>Python</span></div>
        <div><span class="skill-badge"><i class="icon">SQL</i>SQL</span></div>
        <div><span class="skill-badge"><i class="icon">R</i>R</span></div>
        <div><span class="skill-badge"><i class="icon">PW</i>Power BI</span></div>
        <div><span class="skill-badge"><i class="icon">PL</i>Plotly</span></div>
        <div><span class="skill-badge"><i class="icon">FS</i>FastAPI</span></div>
        <div><span class="skill-badge"><i class="icon">ST</i>Streamlit</span></div>
        <div><span class="skill-badge"><i class="icon">NG</i>NetworkX</span></div>
        <div><span class="skill-badge"><i class="icon">SK</i>Scikit-learn</span></div>
        <div><span class="skill-badge"><i class="icon">PT</i>PyTorch</span></div>
        <div><span class="skill-badge"><i class="icon">HF</i>Hugging Face</span></div>
        <div><span class="skill-badge"><i class="icon">SH</i>SHAP</span></div>
        <div><span class="skill-badge"><i class="icon">ET</i>ETL</span></div>
        <div><span class="skill-badge"><i class="icon">GA</i>Google Earth</span></div>
        <div><span class="skill-badge"><i class="icon">JS</i>TypeScript</span></div>
      </div>
    </section>

    <!-- Projects -->
    <section class="projects">
      <h2 class="section-title">Featured Projects</h2>
      
      <div class="project-card reveal" data-project="apguard">
        <h3>APGuard — Accounts Payable Leakage Detection</h3>
        <p>Built a rule-based analytics system to identify payment leakage and contract compliance issues across Accounts Payable transactions. Generated synthetic dataset of 50,000+ invoices with 8 business validation rules.</p>
        <div class="project-tech">
          <span class="tech-tag">Python</span>
          <span class="tech-tag">PostgreSQL</span>
          <span class="tech-tag">FastAPI</span>
          <span class="tech-tag">Streamlit</span>
          <span class="tech-tag">Plotly</span>
        </div>
        <div style="margin-top: 16px;">
          <a href="https://github.com/smitkohale/APGuard" target="_blank" style="color: var(--accent); text-decoration: underline;">GitHub</a>
          <span style="margin-left: 12px; color: var(--muted);">|</span>
          <a href="#" target="_blank" style="color: var(--accent); text-decoration: underline;">Live Demo</a>
        </div>
      </div>

      <div class="project-card reveal" data-project="sentrascope">
        <h3>SentraScope — Environmental Analytics</h3>
        <p>Built environmental analytics platform integrating live air quality, NASA thermal-hotspot, OpenUV, and Earth Engine urbanization data. PostgreSQL schema with Drizzle ORM and Supabase.</p>
        <div class="project-tech">
          <span class="tech-tag">React</span>
          <span class="tech-tag">TypeScript</span>
          <span class="tech-tag">Node.js</span>
          <span class="tech-tag">PostgreSQL</span>
          <span class="tech-tag">Earth Engine</span>
        </div>
        <div style="margin-top: 16px;">
          <a href="https://github.com/smitkohale/Sentrascope" target="_blank" style="color: var(--accent); text-decoration: underline;">GitHub</a>
          <span style="margin-left: 12px; color: var(--muted);">|</span>
          <a href="https://sentrascope.onrender.com/" target="_blank" style="color: var(--accent); text-decoration: underline;">Live Demo</a>
        </div>
      </div>

      <div class="project-card reveal" data-project="review-authenticity">
        <h3>Review Authenticity Engine</h3>
        <p>Two-layer fraud detection system with fine-tuned DistilBERT classifier and reviewer graph analysis using NetworkX. Achieved 100% recall on template/combinatorial tiers.</p>
        <div class="project-tech">
          <span class="tech-tag">PyTorch</span>
          <span class="tech-tag">Hugging Face</span>
          <span class="tech-tag">NetworkX</span>
          <span class="tech-tag">SHAP</span>
          <span class="tech-tag">Streamlit</span>
        </div>
        <div style="margin-top: 16px;">
          <a href="https://github.com/smitkohale/review-authenticity-engine" target="_blank" style="color: var(--accent); text-decoration: underline;">GitHub</a>
          <span style="margin-left: 12px; color: var(--muted);">|</span>
          <a href="https://huggingface.co/Smitvkohale/review-authenticity-engine" target="_blank" style="color: var(--accent); text-decoration: underline;">Hugging Face</a>
        </div>
      </div>
    </section>

    <!-- Experience -->
    <section class="experience">
      <h2 class="section-title">Work Experience</h2>
      
      <div class="timeline">
        
        <div class="experience-item">
          <span class="experience-date">Dec 2025 – Mar 2026</span>
          <h3 class="experience-company">Research Data Analyst</h3>
          <span class="experience-location">MRSAC (Maharashtra Remote Sensing Application Centre) — Nagpur, Maharashtra</span>
          <ul class="experience-bullets">
            <li>Processed multi-temporal satellite imagery across 15+ Maharashtra districts on Google Earth Engine to map urban expansion over a 5-year window.</li>
            <li>Built an early-warning module flagging encroachment hotspots via LULC change-detection, cutting analyst review effort by surfacing only high-priority areas.</li>
            <li>Piped live AQI, thermal-anomaly, and UV data into analytics backend; added natural-language query layer (via OpenAI) for plain English queries.</li>
          </ul>
        </div>

        <div class="experience-item">
          <span class="experience-date">May 2025 – Jun 2025</span>
          <h3 class="experience-company">Data Analyst Intern</h3>
          <span class="experience-location">Dealintra Infotech Pvt. Ltd. — Nagpur, Maharashtra</span>
          <ul class="experience-bullets">
            <li>Processed 50,000+ e-commerce reviews through NLP pipeline (preprocessing, TF-IDF extraction, model evaluation) to predict review authenticity.</li>
            <li>Built review analytics pipeline identifying coordinated manipulation by combining review timing, seller relationships, and linguistic patterns with model predictions.</li>
            <li>Developed interactive dashboards surfacing authenticity scores, seller-credibility metrics, and suspicious activity for fraud investigation.</li>
          </ul>
        </div>

      </div>
    </section>

    <!-- Education -->
    <section style="padding: 40px 0; animation: fadeSlideUp 1s ease-out 1s both;">
      <h2 class="section-title" style="text-align: center;">Education</h2>
      <div style="max-width: 800px; margin: 0 auto; text-align: center;">
        <div style="background: var(--card); border: 1px solid var(--border); border-radius: 16px; padding: 32px; margin: 24px 0;">
          <h3 style="font-size: 1.5rem; margin-bottom: 8px;">B.E. — Computer Science & Engineering</h3>
          <p style="color: var(--muted); margin-bottom: 24px;">SB Jain Institute of Management & Research, Nagpur</p>
          <p style="color: var(--muted);">2022 – 2026</p>
          <p style="color: var(--muted);">Relevant coursework: Machine Learning, Database Systems, Data Warehousing, Computer Networks</p>
        </div>
        <div style="background: var(--card); border: 1px solid var(--border); border-radius: 16px; padding: 24px;;">
          <h4 style="font-size: 0.9rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">12th (HSC)</h4>
          <p style="color: var(--fg);">Taywade College, Nagpur, 2022</p>
          <h4 style="font-size: 0.9rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 8px;">10th (SSC)</h4>
          <p style="color: var(--fg);">Hadas High School, Nagpur, 2020</p>
        </div>
      </div>
    </section>

    <!-- Certifications -->
    <section style="padding: 40px 0; background: var(--bg-secondary); animation: fadeSlideUp 1s ease-out 1.2s both;">
      <h2 class="section-title" style="text-align: center;">Certifications</h2>
      <div style="max-width: 800px; margin: 0 auto;">
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 16px;">
          <div style="background: var(--card); border: 1px solid var(--border); border-radius: 12px; padding: 20px; text-align: center;">
            <div style="font-size: 2rem; margin-bottom: 8px;">✅</div>
            <h4 style="font-size: 0.9rem; margin-bottom: 4px;">Ask Questions to Make Data-Driven Decisions</h4>
            <p style="font-size: 0.75rem; color: var(--muted);">Coursera, Oct 2025</p>
          </div>
          <div style="background: var(--card); border: 1px solid var(--border); border-radius: 12px; padding: 20px; text-align: center;">
            <div style="font-size: 2rem; margin-bottom: 8px;">📊</div>
            <h4 style="font-size: 0.9rem; margin-bottom: 4px;">Big Data Computing</h4>
            <p style="font-size: 0.75rem; color: var(--muted);">NPTEL (IIT), 78%</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer style="padding: 40px 0; text-align: center; color: var(--muted);">
      <p>Built with ❤️ using GitHub Profile README</p>
      <p>© 2026 Smit Kohale</p>
    </footer>
  </div>

  <script>
    // Initialize all elements
    document.addEventListener('DOMContentLoaded', function() {
      // Animate counter numbers
      animateCounters();
      
      // Scroll reveal
      initScrollReveal();
      
      // Parallax background effect
      initParallax();
    });

    function animateCounters() {
      const counters = document.querySelectorAll('.stat-number');
      
      counters.forEach(counter => {
        const target = parseInt(counter.getAttribute('data-target'));
        const duration = 2000;
        const start = 0;
        const startTime = performance.now();
        
        function updateCounter(currentTime) {
          const elapsed = currentTime - startTime;
          const progress = Math.min(elapsed / duration, 1);
          const easeOut = 1 - Math.pow(1 - progress, 3);
          const current = Math.floor(start + (target - start) * easeOut);
          
          counter.textContent = current;
          
          if (progress < 1) {
            requestAnimationFrame(updateCounter);
          }
        }
        
        requestAnimationFrame(updateCounter);
      });
    }

    function initScrollReveal() {
      const reveals = document.querySelectorAll('.reveal');
      
      const revealObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
          }
        });
      }, {
        threshold: 0.1,
        rootMargin: '0px 0px -50px 0px'
      });
      
      reveals.forEach(reveal => {
        revealObserver.observe(reveal);
      });
    }

    function initParallax() {
      const body = document.body;
      
      let ticking = false;
      
      function updateParallax(scrollY) {
        const bgPattern = document.querySelector('.bg-pattern');
        const gridOverlay = document.querySelector('.grid-overlay');
        
        if (bgPattern) {
          bgPattern.style.backgroundPosition = `center ${scrollY * 0.1}px`;
        }
        if (gridOverlay) {
          gridOverlay.style.backgroundPosition = `center ${scrollY * 0.05}px`;
        }
        
        ticking = false;
      }
      
      window.addEventListener('scroll', function() {
        if (!ticking) {
          window.requestAnimationFrame(function() {
            updateParallax(window.scrollY);
          });
          ticking = true;
        }
      }, { passive: true });
    }
  </script>
</body>
</html>
