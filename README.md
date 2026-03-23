<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hanamagouda — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Cabinet+Grotesk:wght@400;500;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --glass: rgba(255,255,255,0.04);
    --glass-border: rgba(255,255,255,0.10);
    --glass-shine: rgba(255,255,255,0.07);
    --accent-cyan: #00ffe0;
    --accent-violet: #9f7aea;
    --accent-rose: #f472b6;
    --accent-amber: #fbbf24;
    --text-primary: #f0f0f8;
    --text-muted: rgba(240,240,248,0.5);
    --text-dim: rgba(240,240,248,0.28);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #050510;
    color: var(--text-primary);
    font-family: 'Cabinet Grotesk', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Cosmic background */
  .bg {
    position: fixed; inset: 0; z-index: 0;
    background:
      radial-gradient(ellipse 80% 60% at 20% 10%, rgba(99,60,180,0.18) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 80% 80%, rgba(0,200,180,0.12) 0%, transparent 55%),
      radial-gradient(ellipse 50% 40% at 60% 30%, rgba(244,114,182,0.08) 0%, transparent 50%),
      #050510;
  }

  /* Floating orbs */
  .orb {
    position: fixed; border-radius: 50%; filter: blur(80px); z-index: 0; pointer-events: none;
    animation: drift 20s ease-in-out infinite;
  }
  .orb-1 { width:500px; height:500px; background:rgba(99,60,180,0.15); top:-100px; left:-100px; animation-delay:0s; }
  .orb-2 { width:400px; height:400px; background:rgba(0,255,224,0.08); bottom:-80px; right:-80px; animation-delay:-7s; }
  .orb-3 { width:300px; height:300px; background:rgba(244,114,182,0.07); top:40%; left:60%; animation-delay:-13s; }

  @keyframes drift {
    0%,100% { transform: translate(0,0) scale(1); }
    33% { transform: translate(30px,-20px) scale(1.05); }
    66% { transform: translate(-20px,30px) scale(0.97); }
  }

  .wrapper {
    position: relative; z-index: 1;
    max-width: 860px; margin: 0 auto;
    padding: 48px 24px 80px;
  }

  /* Glass card base */
  .glass-card {
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    backdrop-filter: blur(24px);
    -webkit-backdrop-filter: blur(24px);
    position: relative;
    overflow: hidden;
  }

  .glass-card::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: inherit;
    background: linear-gradient(135deg, rgba(255,255,255,0.06) 0%, transparent 50%, rgba(255,255,255,0.02) 100%);
    pointer-events: none;
  }

  /* Shine sweep on hover */
  .glass-card::after {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 60%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.05), transparent);
    transform: skewX(-20deg);
    transition: left 0.6s ease;
    pointer-events: none;
  }
  .glass-card:hover::after { left: 150%; }

  /* ── HERO ── */
  .hero {
    padding: 48px 48px 40px;
    margin-bottom: 20px;
    animation: fadeUp 0.8s ease both;
  }

  .hero-inner {
    display: flex;
    align-items: center;
    gap: 40px;
  }

  .avatar-wrap {
    position: relative; flex-shrink: 0;
  }

  .avatar-glow {
    position: absolute; inset: -12px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--accent-cyan), var(--accent-violet), var(--accent-rose), var(--accent-cyan));
    filter: blur(14px);
    opacity: 0.5;
    animation: spin 8s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .avatar-ring {
    position: absolute; inset: -4px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--accent-cyan), var(--accent-violet), var(--accent-rose), var(--accent-cyan));
    animation: spin 8s linear infinite;
    padding: 2px;
  }

  .avatar-ring-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: #0a0a1e;
  }

  .avatar {
    width: 110px; height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, #1a1a3e, #2a1a4e);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Clash Display', sans-serif;
    font-size: 32px; font-weight: 700;
    color: var(--accent-cyan);
    position: relative; z-index: 1;
    letter-spacing: -1px;
    text-shadow: 0 0 20px rgba(0,255,224,0.6);
  }

  .hero-text { flex: 1; }

  .name {
    font-family: 'Clash Display', sans-serif;
    font-size: 42px; font-weight: 700;
    letter-spacing: -1.5px;
    line-height: 1;
    background: linear-gradient(135deg, #ffffff 30%, var(--accent-cyan) 70%, var(--accent-violet) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .handle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; font-weight: 300;
    color: var(--accent-cyan);
    letter-spacing: 0.04em;
    margin-bottom: 14px;
    opacity: 0.8;
  }

  .bio {
    font-size: 15px;
    color: var(--text-muted);
    line-height: 1.6;
    max-width: 420px;
    margin-bottom: 20px;
  }

  .pill-row { display: flex; flex-wrap: wrap; gap: 8px; }

  .pill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; font-weight: 400;
    padding: 5px 14px;
    border-radius: 100px;
    border: 1px solid;
    letter-spacing: 0.03em;
    transition: all 0.2s;
  }

  .pill:hover { transform: translateY(-1px); }

  .pill-cyan { color: var(--accent-cyan); border-color: rgba(0,255,224,0.3); background: rgba(0,255,224,0.06); }
  .pill-violet { color: var(--accent-violet); border-color: rgba(159,122,234,0.3); background: rgba(159,122,234,0.06); }
  .pill-rose { color: var(--accent-rose); border-color: rgba(244,114,182,0.3); background: rgba(244,114,182,0.06); }
  .pill-amber { color: var(--accent-amber); border-color: rgba(251,191,36,0.3); background: rgba(251,191,36,0.06); }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 20px;
    animation: fadeUp 0.8s 0.1s ease both;
  }

  .stat-card {
    padding: 22px 16px;
    text-align: center;
    transition: transform 0.2s;
  }

  .stat-card:hover { transform: translateY(-3px); }

  .stat-icon {
    font-size: 18px; margin-bottom: 8px;
    display: block;
  }

  .stat-num {
    font-family: 'Clash Display', sans-serif;
    font-size: 28px; font-weight: 700;
    letter-spacing: -1px;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 0.05em;
    text-transform: uppercase;
    font-family: 'JetBrains Mono', monospace;
  }

  .num-cyan { color: var(--accent-cyan); text-shadow: 0 0 20px rgba(0,255,224,0.4); }
  .num-violet { color: var(--accent-violet); text-shadow: 0 0 20px rgba(159,122,234,0.4); }
  .num-rose { color: var(--accent-rose); text-shadow: 0 0 20px rgba(244,114,182,0.4); }
  .num-amber { color: var(--accent-amber); text-shadow: 0 0 20px rgba(251,191,36,0.4); }

  /* ── TECH STACK ── */
  .section-wrap {
    margin-bottom: 20px;
    animation: fadeUp 0.8s 0.2s ease both;
  }

  .section-header {
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 16px; padding: 0 4px;
  }

  .section-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; font-weight: 400;
    color: var(--text-dim);
    text-transform: uppercase;
    letter-spacing: 0.12em;
  }

  .section-line {
    flex: 1; height: 1px;
    background: linear-gradient(90deg, var(--glass-border), transparent);
  }

  .tech-wrap { padding: 28px 28px; }

  .tech-grid {
    display: flex; flex-wrap: wrap; gap: 10px;
  }

  .tech-chip {
    display: flex; align-items: center; gap: 8px;
    padding: 8px 16px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--text-muted);
    transition: all 0.25s;
    cursor: default;
  }

  .tech-chip:hover {
    background: rgba(255,255,255,0.07);
    border-color: rgba(255,255,255,0.15);
    color: var(--text-primary);
    transform: translateY(-2px);
  }

  .tech-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }

  /* ── PROJECTS ── */
  .projects-wrap {
    padding: 28px;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .proj-card {
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px;
    padding: 20px;
    transition: all 0.25s;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }

  .proj-card::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: inherit;
    background: linear-gradient(135deg, rgba(255,255,255,0.04) 0%, transparent 60%);
    pointer-events: none;
  }

  .proj-card:hover {
    border-color: rgba(0,255,224,0.2);
    background: rgba(0,255,224,0.03);
    transform: translateY(-2px);
  }

  .proj-card:hover .proj-glow { opacity: 1; }

  .proj-glow {
    position: absolute; top: 0; left: 0;
    width: 100%; height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent-cyan), transparent);
    opacity: 0; transition: opacity 0.3s;
  }

  .proj-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; font-weight: 500;
    color: #7dd3fc;
    margin-bottom: 6px;
  }

  .proj-desc {
    font-size: 12px;
    color: var(--text-dim);
    line-height: 1.5;
    margin-bottom: 14px;
  }

  .proj-footer {
    display: flex; align-items: center; gap: 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--text-dim);
  }

  .lang-dot { display: inline-block; width: 8px; height: 8px; border-radius: 50%; margin-right: 5px; }

  /* ── CONTRIBUTION GRAPH ── */
  .contrib-wrap { padding: 28px; animation: fadeUp 0.8s 0.35s ease both; }

  .contrib-grid { display: flex; gap: 3px; flex-wrap: wrap; }

  .contrib-cell {
    width: 12px; height: 12px; border-radius: 3px;
    transition: transform 0.1s;
    cursor: default;
  }

  .contrib-cell:hover { transform: scale(1.4); }

  /* ── CONNECT ── */
  .connect-wrap { padding: 32px 28px; animation: fadeUp 0.8s 0.4s ease both; }

  .connect-grid {
    display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px;
  }

  .connect-btn {
    display: flex; align-items: center; gap: 12px;
    padding: 16px 20px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 12px;
    text-decoration: none;
    color: var(--text-muted);
    font-size: 13px;
    transition: all 0.25s;
    cursor: pointer;
  }

  .connect-btn:hover {
    background: rgba(255,255,255,0.06);
    border-color: rgba(255,255,255,0.15);
    color: var(--text-primary);
    transform: translateX(4px);
  }

  .connect-icon {
    width: 36px; height: 36px; border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px; flex-shrink: 0;
  }

  .connect-label { font-size: 11px; color: var(--text-dim); font-family: 'JetBrains Mono', monospace; margin-top: 1px; }

  /* ── FOOTER QUOTE ── */
  .quote {
    text-align: center;
    padding: 32px 28px;
    font-family: 'Clash Display', sans-serif;
    font-size: 18px; font-weight: 500;
    color: var(--text-dim);
    letter-spacing: -0.3px;
    line-height: 1.5;
    animation: fadeUp 0.8s 0.5s ease both;
  }

  .quote span {
    background: linear-gradient(90deg, var(--accent-cyan), var(--accent-violet));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }

  /* Animations */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: rgba(255,255,255,0.1); border-radius: 3px; }
</style>
</head>
<body>

<div class="bg"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="wrapper">

  <!-- HERO -->
  <div class="glass-card hero">
    <div class="hero-inner">
      <div class="avatar-wrap">
        <div class="avatar-glow"></div>
        <div class="avatar-ring"><div class="avatar-ring-inner"></div></div>
        <div class="avatar">HP</div>
      </div>
      <div class="hero-text">
        <div class="name">Hanamagouda Patil</div>
        <div class="handle">@hanamagouda9611 · he/him</div>
        <div class="bio">Software Engineer based in Bengaluru, India. I build scalable APIs, geospatial data pipelines, and clean backend systems that just work.</div>
        <div class="pill-row">
          <span class="pill pill-cyan">Software Engineer</span>
          <span class="pill pill-violet">Bengaluru, India</span>
          <span class="pill pill-rose">Open to Collabs</span>
          <span class="pill pill-amber">Full Stack</span>
        </div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-grid">
    <div class="glass-card stat-card">
      <span class="stat-icon">⬡</span>
      <div class="stat-num num-cyan">59</div>
      <div class="stat-label">Contributions</div>
    </div>
    <div class="glass-card stat-card">
      <span class="stat-icon">◈</span>
      <div class="stat-num num-violet">12</div>
      <div class="stat-label">Repositories</div>
    </div>
    <div class="glass-card stat-card">
      <span class="stat-icon">◎</span>
      <div class="stat-num num-rose">2</div>
      <div class="stat-label">Followers</div>
    </div>
    <div class="glass-card stat-card">
      <span class="stat-icon">◇</span>
      <div class="stat-num num-amber">5</div>
      <div class="stat-label">Following</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section-wrap">
    <div class="section-header">
      <span class="section-title">tech stack</span>
      <div class="section-line"></div>
    </div>
    <div class="glass-card tech-wrap">
      <div class="tech-grid">
        <div class="tech-chip"><span class="tech-dot" style="background:#3B82F6;box-shadow:0 0 6px #3B82F6;"></span>Python</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#009688;box-shadow:0 0 6px #009688;"></span>FastAPI</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#F7DF1E;box-shadow:0 0 6px #F7DF1E;"></span>JavaScript</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#326CE5;box-shadow:0 0 6px #326CE5;"></span>Kubernetes</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#2496ED;box-shadow:0 0 6px #2496ED;"></span>Docker</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#4169E1;box-shadow:0 0 6px #4169E1;"></span>PostgreSQL</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#139C5A;box-shadow:0 0 6px #139C5A;"></span>PostGIS</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#F37626;box-shadow:0 0 6px #F37626;"></span>Jupyter</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#150458;box-shadow:0 0 6px #818CF8;"></span>Pandas</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#F05032;box-shadow:0 0 6px #F05032;"></span>Git</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#FF9900;box-shadow:0 0 6px #FF9900;"></span>AWS</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#000000;box-shadow:0 0 6px #aaa;"></span>Vercel</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#4A154B;box-shadow:0 0 6px #C084FC;"></span>GraphQL</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#4EC9B0;box-shadow:0 0 6px #4EC9B0;"></span>REST APIs</div>
        <div class="tech-chip"><span class="tech-dot" style="background:#21C55D;box-shadow:0 0 6px #21C55D;"></span>Shell</div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section-wrap">
    <div class="section-header">
      <span class="section-title">featured projects</span>
      <div class="section-line"></div>
    </div>
    <div class="glass-card projects-wrap">
      <div class="projects-grid">

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">fastapi-jwt-rbac</div>
          <div class="proj-desc">Secure FastAPI boilerplate with JWT auth and role-based access control. Production-ready from day one.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#3B82F6;"></span>Python</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">kubernetes-yaml-examples</div>
          <div class="proj-desc">Battle-tested K8s manifests and YAML templates for deploying containerized apps at scale.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#89E051;"></span>Shell</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">geopandas-to-postgis</div>
          <div class="proj-desc">Geospatial data pipeline: ingest, process and load shapefile data into PostGIS with GeoPandas.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#F37626;"></span>Jupyter</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">etl-pipeline</div>
          <div class="proj-desc">Modular ETL pipeline for data extraction, transformation, and loading at scale with Python.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#3B82F6;"></span>Python</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">fastapi-geocode</div>
          <div class="proj-desc">REST API for geocoding and reverse geocoding — fast, clean, and deployable in minutes.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#3B82F6;"></span>Python</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

        <div class="proj-card">
          <div class="proj-glow"></div>
          <div class="proj-name">map-poi-app</div>
          <div class="proj-desc">Interactive map app for exploring Points of Interest with dynamic filtering and clean JS UI.</div>
          <div class="proj-footer">
            <span><span class="lang-dot" style="background:#F7DF1E;"></span>JavaScript</span>
            <span>★ —</span><span>⑂ —</span>
          </div>
        </div>

      </div>
    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="section-wrap">
    <div class="section-header">
      <span class="section-title">contribution activity · 2026</span>
      <div class="section-line"></div>
    </div>
    <div class="glass-card contrib-wrap">
      <div class="contrib-grid" id="cGrid"></div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-wrap">
    <div class="section-header">
      <span class="section-title">connect</span>
      <div class="section-line"></div>
    </div>
    <div class="glass-card connect-wrap">
      <div class="connect-grid">
        <a class="connect-btn" href="https://hanamaportfolio.vercel.app/" target="_blank">
          <div class="connect-icon" style="background:rgba(0,255,224,0.08);border:1px solid rgba(0,255,224,0.2);">🌐</div>
          <div>
            <div>Portfolio</div>
            <div class="connect-label">hanamaportfolio.vercel.app</div>
          </div>
        </a>
        <a class="connect-btn" href="https://www.linkedin.com/in/hanamagoud-patil-897033148/" target="_blank">
          <div class="connect-icon" style="background:rgba(10,102,194,0.12);border:1px solid rgba(10,102,194,0.3);">💼</div>
          <div>
            <div>LinkedIn</div>
            <div class="connect-label">hanamagoud-patil-897033148</div>
          </div>
        </a>
        <a class="connect-btn" href="mailto:hanamagoudpatil9611@gmail.com">
          <div class="connect-icon" style="background:rgba(234,67,53,0.1);border:1px solid rgba(234,67,53,0.25);">📧</div>
          <div>
            <div>Email</div>
            <div class="connect-label">hanamagoudpatil9611@gmail.com</div>
          </div>
        </a>
        <a class="connect-btn" href="https://github.com/hanamagouda9611" target="_blank">
          <div class="connect-icon" style="background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.12);">🐙</div>
          <div>
            <div>GitHub</div>
            <div class="connect-label">@hanamagouda9611</div>
          </div>
        </a>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="glass-card quote">
    "First, solve the problem.<br><span>Then, write the code.</span>"
  </div>

</div>

<script>
  // Contribution graph
  const grid = document.getElementById('cGrid');
  const levels = [0,0,0,0,1,1,1,2,2,3,4];
  const colors = [
    'rgba(255,255,255,0.05)',
    'rgba(0,255,224,0.15)',
    'rgba(0,255,224,0.35)',
    'rgba(0,255,224,0.6)',
    'rgba(0,255,224,0.9)'
  ];
  for (let i = 0; i < 224; i++) {
    const lvl = levels[Math.floor(Math.random() * levels.length)];
    const cell = document.createElement('div');
    cell.className = 'contrib-cell';
    cell.style.background = colors[lvl];
    if (lvl > 0) cell.style.boxShadow = `0 0 ${lvl * 3}px rgba(0,255,224,${lvl * 0.15})`;
    grid.appendChild(cell);
  }
</script>
</body>
</html>
