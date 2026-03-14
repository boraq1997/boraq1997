<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Boraq Nezar - GitHub Profile</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
    *{box-sizing:border-box;margin:0;padding:0}
    :root{
      --accent:#00E5A0;
      --accent2:#0AF;
      --bg:#0A0F1E;
      --card:#0E1529;
      --card2:#111A30;
      --border:#1E2D50;
      --text:#E8F0FF;
      --muted:#5A6E99;
      --mono:'Space Mono',monospace;
      --sans:'Syne',sans-serif;
    }
    body{background:var(--bg);color:var(--text);font-family:var(--sans)}
    .wrap{max-width:860px;margin:0 auto;padding:2rem 1.5rem 3rem}

    .hero{display:grid;grid-template-columns:auto 1fr;gap:2rem;align-items:center;padding:2.5rem;background:var(--card);border:1px solid var(--border);border-radius:16px;margin-bottom:1.5rem;position:relative;overflow:hidden}
    .hero::before{content:'';position:absolute;top:-80px;right:-80px;width:260px;height:260px;background:radial-gradient(circle,rgba(0,229,160,0.08) 0%,transparent 70%);pointer-events:none}
    .avatar{width:88px;height:88px;border-radius:50%;background:linear-gradient(135deg,#00E5A0,#00AAFF);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:26px;font-weight:700;color:#0A0F1E;flex-shrink:0}
    .hero-info h1{font-size:28px;font-weight:800;letter-spacing:-0.5px;line-height:1.1}
    .hero-info h1 span{color:var(--accent)}
    .hero-info p{color:var(--muted);font-size:14px;margin-top:6px;font-family:var(--mono);letter-spacing:0.3px}
    .hero-info .desc{color:#8EAAD8;font-size:14px;margin-top:12px;line-height:1.6;font-family:var(--sans)}
    .badges{display:flex;flex-wrap:wrap;gap:8px;margin-top:16px}
    .badge{font-family:var(--mono);font-size:11px;padding:4px 10px;border-radius:20px;border:1px solid;letter-spacing:0.5px}
    .b-green{color:var(--accent);border-color:rgba(0,229,160,0.3);background:rgba(0,229,160,0.06)}
    .b-blue{color:var(--accent2);border-color:rgba(0,170,255,0.3);background:rgba(0,170,255,0.06)}
    .b-purple{color:#B899FF;border-color:rgba(184,153,255,0.3);background:rgba(184,153,255,0.06)}

    .links{display:flex;gap:10px;margin-bottom:1.5rem;flex-wrap:wrap}
    .link-btn{font-family:var(--mono);font-size:12px;padding:8px 16px;border-radius:8px;border:1px solid var(--border);background:var(--card2);color:var(--muted);text-decoration:none;cursor:pointer;transition:all 0.2s;display:flex;align-items:center;gap:6px}
    .link-btn:hover{border-color:var(--accent);color:var(--accent)}

    .sec-title{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px;display:flex;align-items:center;gap:8px}
    .sec-title::after{content:'';flex:1;height:1px;background:var(--border)}

    .stats-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:1.5rem}
    .stat-card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.2rem 1rem;text-align:center}
    .stat-num{font-family:var(--mono);font-size:26px;font-weight:700;color:var(--accent);line-height:1}
    .stat-label{font-size:12px;color:var(--muted);margin-top:6px;font-family:var(--mono)}

    .skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(120px,1fr));gap:10px;margin-bottom:1.5rem}
    .skill{background:var(--card);border:1px solid var(--border);border-radius:10px;padding:10px 12px;display:flex;align-items:center;gap:8px;font-size:13px;font-weight:600;transition:border-color 0.2s}
    .skill:hover{border-color:var(--accent)}
    .skill-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}
    .dot-green{background:var(--accent)}
    .dot-blue{background:var(--accent2)}
    .dot-purple{background:#B899FF}
    .dot-orange{background:#FF9040}

    .focus-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;margin-bottom:1.5rem}
    .focus-card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.2rem}
    .focus-card h3{font-size:13px;font-weight:700;margin-bottom:6px;display:flex;align-items:center;gap:8px}
    .focus-card p{font-size:12px;color:var(--muted);line-height:1.6;font-family:var(--mono)}

    .contact{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.5rem;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:16px}
    .contact-info h3{font-size:16px;font-weight:700}
    .contact-info p{font-size:13px;color:var(--muted);font-family:var(--mono);margin-top:4px}
    .contact-cta{font-family:var(--mono);font-size:13px;padding:10px 20px;border-radius:8px;background:var(--accent);color:#0A0F1E;font-weight:700;border:none;cursor:pointer;letter-spacing:0.3px;transition:opacity 0.2s;text-decoration:none}
    .contact-cta:hover{opacity:0.85}

    .location{font-family:var(--mono);font-size:12px;color:var(--muted);display:flex;align-items:center;gap:4px;margin-top:8px}

    @media(max-width:580px){
      .hero{grid-template-columns:1fr;text-align:center}
      .hero::before{display:none}
      .badges{justify-content:center}
      .focus-grid{grid-template-columns:1fr}
      .contact{flex-direction:column;text-align:center}
      .links{justify-content:center}
    }
  </style>
</head>
<body>
<div class="wrap">

  <div class="hero">
    <div class="avatar">BN</div>
    <div class="hero-info">
      <h1>Boraq <span>Nezar</span></h1>
      <p>// full-stack web developer & freelancer</p>
      <div class="location">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
        Iraq 🇮🇶
      </div>
      <p class="desc">Building robust, scalable, and user-friendly applications with strong focus on clean architecture, performance, and great UX.</p>
      <div class="badges">
        <span class="badge b-green">Laravel</span>
        <span class="badge b-blue">Vue.js</span>
        <span class="badge b-blue">Angular</span>
        <span class="badge b-green">PHP</span>
        <span class="badge b-purple">Python</span>
        <span class="badge b-purple">AI / ML</span>
        <span class="badge b-blue">Docker</span>
        <span class="badge b-green">Linux</span>
      </div>
    </div>
  </div>

  <div class="links">
    <a class="link-btn" href="https://boraq.site" target="_blank">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
      boraq.site
    </a>
    <a class="link-btn" href="mailto:boraqnz@gmail.com">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      boraqnz@gmail.com
    </a>
    <a class="link-btn" href="https://www.linkedin.com/in/boraq-nezar-836919157" target="_blank">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a class="link-btn" href="https://github.com/boraq1997" target="_blank">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      GitHub
    </a>
  </div>

  <div class="sec-title">activity</div>
  <div class="stats-grid">
    <div class="stat-card"><div class="stat-num">7+</div><div class="stat-label">yrs experience</div></div>
    <div class="stat-card"><div class="stat-num">25+</div><div class="stat-label">projects built</div></div>
    <div class="stat-card"><div class="stat-num">8+</div><div class="stat-label">tech stacks</div></div>
  </div>

  <div class="sec-title">tech stack</div>
  <div class="skills-grid">
    <div class="skill"><span class="skill-dot dot-green"></span>Laravel</div>
    <div class="skill"><span class="skill-dot dot-blue"></span>Vue.js</div>
    <div class="skill"><span class="skill-dot dot-blue"></span>Angular</div>
    <div class="skill"><span class="skill-dot dot-green"></span>PHP</div>
    <div class="skill"><span class="skill-dot dot-purple"></span>Python</div>
    <div class="skill"><span class="skill-dot dot-blue"></span>JavaScript</div>
    <div class="skill"><span class="skill-dot dot-orange"></span>Docker</div>
    <div class="skill"><span class="skill-dot dot-green"></span>MySQL</div>
    <div class="skill"><span class="skill-dot dot-blue"></span>PostgreSQL</div>
    <div class="skill"><span class="skill-dot dot-purple"></span>MongoDB</div>
    <div class="skill"><span class="skill-dot dot-orange"></span>Linux</div>
    <div class="skill"><span class="skill-dot dot-green"></span>Flutter</div>
    <div class="skill"><span class="skill-dot dot-purple"></span>Pandas</div>
    <div class="skill"><span class="skill-dot dot-blue"></span>Git</div>
    <div class="skill"><span class="skill-dot dot-orange"></span>Flask</div>
    <div class="skill"><span class="skill-dot dot-purple"></span>NumPy</div>
  </div>

  <div class="sec-title">current focus</div>
  <div class="focus-grid">
    <div class="focus-card">
      <h3>
        <span style="width:20px;height:20px;border-radius:5px;background:rgba(0,229,160,0.12);display:inline-flex;align-items:center;justify-content:center">
          <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="#00E5A0" stroke-width="2.5"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
        </span>
        AI & Data Analysis
      </h3>
      <p>Working on AI projects using Pandas, NumPy, and Matplotlib. Exploring machine learning workflows and data pipelines.</p>
    </div>
    <div class="focus-card">
      <h3>
        <span style="width:20px;height:20px;border-radius:5px;background:rgba(0,170,255,0.12);display:inline-flex;align-items:center;justify-content:center">
          <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="#00AAFF" stroke-width="2.5"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
        </span>
        Python & Tkinter
      </h3>
      <p>Building desktop GUI applications with Tkinter. Deepening Python skills for automation and AI-driven workflows.</p>
    </div>
  </div>

  <div class="contact">
    <div class="contact-info">
      <h3>Let's build something great</h3>
      <p>boraqnz@gmail.com</p>
    </div>
    <a class="contact-cta" href="mailto:boraqnz@gmail.com">Get in touch →</a>
  </div>

</div>
</body>
</html>
