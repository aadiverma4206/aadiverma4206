<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aditya Kumar — Full Stack & Mobile Developer</title>
<style>
  :root{
    --bg: #14171F;
    --surface: #1C2130;
    --surface-2: #232A3D;
    --copper: #E8A33D;
    --teal: #3EC1D3;
    --ink: #F0EDE5;
    --ink-dim: #A7AEC0;
    --line: #2E3548;
  }
  *{ margin:0; padding:0; box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    background:var(--bg);
    color:var(--ink);
    font-family: 'Segoe UI', 'Inter', system-ui, sans-serif;
    line-height:1.5;
    overflow-x:hidden;
  }
  h1,h2,h3, .mono{ font-family:'Consolas','SFMono-Regular','Cascadia Code',monospace; }

  /* ---------- circuit background ---------- */
  .circuit-bg{
    position:fixed; inset:0; z-index:0; opacity:0.35; pointer-events:none;
  }
  .circuit-bg path{
    fill:none; stroke:var(--teal); stroke-width:1.4;
    stroke-dasharray:900; stroke-dashoffset:900;
    animation: draw 3.2s ease-out forwards;
  }
  .circuit-bg path.copper{ stroke:var(--copper); animation-delay:.3s; }
  .circuit-bg circle{
    fill:var(--copper); opacity:0; animation: dotpop .6s ease-out forwards;
  }
  @keyframes draw{ to{ stroke-dashoffset:0; } }
  @keyframes dotpop{ to{ opacity:1; } }

  main{ position:relative; z-index:1; max-width:920px; margin:0 auto; padding:0 28px; }

  /* ---------- hero ---------- */
  .hero{
    min-height:78vh; display:flex; flex-direction:column; justify-content:center;
    padding-top:40px;
  }
  .hero .tag{ color:var(--copper); font-size:0.95rem; letter-spacing:0.02em; margin-bottom:10px; }
  .hero h1{
    font-size:clamp(2.4rem, 6vw, 4.2rem);
    font-weight:700; color:var(--ink); line-height:1.05;
  }
  .hero .role{
    margin-top:14px; font-size:clamp(1.1rem,2.4vw,1.5rem); color:var(--teal);
    min-height:1.6em; border-right:2px solid var(--teal); padding-right:4px; white-space:nowrap; overflow:hidden; display:inline-block;
  }
  .hero p.desc{
    margin-top:22px; max-width:60ch; color:var(--ink-dim); font-size:1.02rem;
  }
  .hero .links{ margin-top:28px; display:flex; gap:22px; flex-wrap:wrap; }
  .hero .links a{
    color:var(--ink); text-decoration:none; font-size:0.95rem; position:relative; padding-bottom:3px;
  }
  .hero .links a::after{
    content:''; position:absolute; left:0; bottom:0; width:0; height:1px; background:var(--copper);
    transition: width .3s ease;
  }
  .hero .links a:hover::after{ width:100%; }

  /* ---------- section shell ---------- */
  section{ padding:64px 0; border-top:1px solid var(--line); }
  section h2{
    font-size:1.15rem; color:var(--copper); font-weight:600; margin-bottom:32px;
    display:flex; align-items:center; gap:12px;
  }
  section h2::after{ content:''; flex:1; height:1px; background:var(--line); }

  /* ---------- stack ---------- */
  .stack-grid{ display:grid; grid-template-columns:repeat(auto-fit,minmax(210px,1fr)); gap:24px; }
  .stack-cat h3{ font-size:0.82rem; color:var(--ink-dim); font-weight:500; margin-bottom:10px; text-transform:none; }
  .chips{ display:flex; flex-wrap:wrap; gap:8px; }
  .chip{
    font-size:0.85rem; padding:5px 12px; border:1px solid var(--line); border-radius:3px;
    color:var(--ink); background:var(--surface);
  }

  /* ---------- experience timeline ---------- */
  .timeline{ position:relative; padding-left:26px; }
  .timeline::before{
    content:''; position:absolute; left:6px; top:6px; bottom:6px; width:1px; background:var(--line);
  }
  .tl-item{ position:relative; margin-bottom:38px; }
  .tl-item:last-child{ margin-bottom:0; }
  .tl-item::before{
    content:''; position:absolute; left:-26px; top:5px; width:9px; height:9px; border-radius:50%;
    background:var(--bg); border:2px solid var(--teal);
  }
  .tl-item .yr{ color:var(--teal); font-size:0.85rem; margin-bottom:4px; }
  .tl-item h3{ font-size:1.05rem; font-weight:600; color:var(--ink); }
  .tl-item .org{ color:var(--ink-dim); font-size:0.92rem; margin-bottom:8px; }
  .tl-item ul{ padding-left:18px; color:var(--ink-dim); font-size:0.92rem; }
  .tl-item li{ margin-bottom:4px; }

  /* ---------- education & certs ---------- */
  .two-col{ display:grid; grid-template-columns:1fr 1fr; gap:40px; }
  .edu-item{ margin-bottom:18px; }
  .edu-item .deg{ font-weight:600; color:var(--ink); }
  .edu-item .meta{ color:var(--ink-dim); font-size:0.9rem; }
  .cert-list{ list-style:none; }
  .cert-list li{
    padding:10px 0; border-bottom:1px solid var(--line); color:var(--ink-dim); font-size:0.92rem;
    display:flex; justify-content:space-between; gap:12px;
  }
  .cert-list li span.dot{ color:var(--copper); margin-right:8px; }

  footer{
    padding:40px 0 60px; text-align:center; color:var(--ink-dim); font-size:0.85rem;
  }
  footer .name{ color:var(--copper); }

  @media (max-width:640px){
    .two-col{ grid-template-columns:1fr; }
    .hero .role{ white-space:normal; border-right:none; }
  }

  @media (prefers-reduced-motion: reduce){
    .circuit-bg path{ animation:none; stroke-dashoffset:0; }
    .circuit-bg circle{ animation:none; opacity:1; }
  }
</style>
</head>
<body>

<svg class="circuit-bg" viewBox="0 0 1000 1200" preserveAspectRatio="none">
  <path d="M0,120 L200,120 L200,280 L480,280 L480,60 L900,60" />
  <path class="copper" d="M0,420 L140,420 L140,560 L400,560 L400,700 L1000,700" />
  <path d="M0,860 L260,860 L260,980 L620,980 L620,1120 L1000,1120" />
  <circle cx="200" cy="120" r="4" style="animation-delay:1.1s"/>
  <circle cx="480" cy="280" r="4" style="animation-delay:1.4s"/>
  <circle cx="140" cy="420" r="4" style="animation-delay:1.7s"/>
  <circle cx="400" cy="700" r="4" style="animation-delay:2s"/>
  <circle cx="260" cy="860" r="4" style="animation-delay:2.3s"/>
  <circle cx="620" cy="1120" r="4" style="animation-delay:2.6s"/>
</svg>

<main>

  <section class="hero" style="border-top:none;">
    <div class="tag mono">// full stack &amp; mobile developer</div>
    <h1>Aditya Kumar</h1>
    <span class="role mono" id="typedRole"></span>
    <p class="desc">Building secure REST APIs, role-based systems and cross-platform apps with Flutter, React, Angular and Node.js — with hands-on delivery for government (NIC) and private-sector products.</p>
    <div class="links">
      <a href="https://linkedin.com" target="_blank">LinkedIn ↗</a>
      <a href="https://your-portfolio-link.com" target="_blank">Portfolio ↗</a>
      <a href="https://github.com/aadiverma4206" target="_blank">GitHub ↗</a>
    </div>
  </section>

  <section id="stack">
    <h2>Tech Stack</h2>
    <div class="stack-grid">
      <div class="stack-cat">
        <h3>Backend</h3>
        <div class="chips">
          <span class="chip">Node.js</span><span class="chip">Express.js</span>
          <span class="chip">.NET Core MVC</span><span class="chip">Java</span>
          <span class="chip">REST APIs</span><span class="chip">JWT</span><span class="chip">Swagger</span>
        </div>
      </div>
      <div class="stack-cat">
        <h3>Frontend &amp; Mobile</h3>
        <div class="chips">
          <span class="chip">Flutter</span><span class="chip">React.js</span>
          <span class="chip">Angular</span><span class="chip">Ionic</span>
          <span class="chip">TypeScript</span><span class="chip">Tailwind CSS</span>
        </div>
      </div>
      <div class="stack-cat">
        <h3>Database</h3>
        <div class="chips">
          <span class="chip">MySQL</span><span class="chip">MariaDB</span>
          <span class="chip">MongoDB</span><span class="chip">Firebase</span>
        </div>
      </div>
      <div class="stack-cat">
        <h3>Tools &amp; Concepts</h3>
        <div class="chips">
          <span class="chip">Git</span><span class="chip">Docker</span><span class="chip">Postman</span>
          <span class="chip">Redis</span><span class="chip">Railway</span><span class="chip">Render</span>
          <span class="chip">Design Patterns</span><span class="chip">Agile / Scrum</span>
        </div>
      </div>
    </div>
  </section>

  <section id="experience">
    <h2>Experience</h2>
    <div class="timeline">
      <div class="tl-item">
        <div class="yr mono">2026</div>
        <h3>Full Stack Developer</h3>
        <div class="org">Botivate Services LLP — Zold Gold App (Live on PlayStore)</div>
        <ul>
          <li>Built the app with Flutter, TypeScript, Prisma, Supabase and Socket-based OTP auth.</li>
          <li>Implemented role-based access, home page, payment integration and location map.</li>
          <li>Integrated REST APIs and optimized client-side data management.</li>
        </ul>
      </div>
      <div class="tl-item">
        <div class="yr mono">2026</div>
        <h3>Web Developer</h3>
        <div class="org">NIC Chhattisgarh</div>
        <ul>
          <li>Developed a Database Comment Management System using Ionic, Angular, Node.js and MySQL.</li>
        </ul>
      </div>
      <div class="tl-item">
        <div class="yr mono">2026</div>
        <h3>Mobile App Developer</h3>
        <div class="org">National Informatics Centre (NIC), Raipur</div>
        <ul>
          <li>Built a Drug Tracking System for the Food &amp; Drugs Administration with Flutter, Node.js, Express.js and MySQL.</li>
          <li>Developed secure JWT-based REST APIs for inventory, stock, invoice, sales and inspection management.</li>
          <li>Used Git, Swagger, Railway, Render and Postman for deployment and testing.</li>
        </ul>
      </div>
    </div>
  </section>

  <section id="education">
    <h2>Education &amp; Certifications</h2>
    <div class="two-col">
      <div>
        <div class="edu-item">
          <div class="deg">M.Sc. (IT)</div>
          <div class="meta">PRSU, SOS CS &amp; IT — 2026 · 83.59%</div>
        </div>
        <div class="edu-item">
          <div class="deg">B.Sc. (IT)</div>
          <div class="meta">PRSU, GNSCR — 2024 · 74.2%</div>
        </div>
      </div>
      <ul class="cert-list">
        <li><span><span class="dot">▸</span>NIC Chhattisgarh Internship</span><span>6 months</span></li>
        <li><span><span class="dot">▸</span>Adyant Softech Internship</span><span>3 months</span></li>
        <li><span><span class="dot">▸</span>Flutter Development</span><span>Tutedude</span></li>
        <li><span><span class="dot">▸</span>Data Analytics</span><span>CodeWithHarry</span></li>
      </ul>
    </div>
  </section>

  <footer>
    Designed &amp; built by <span class="name">Aditya Kumar</span> — reach out via LinkedIn or Portfolio above.
  </footer>

</main>

<script>
  const roles = ["Flutter Developer", "Node.js & Express APIs", "React.js / Angular Engineer", "REST API & Auth Systems"];
  const el = document.getElementById('typedRole');
  let ri = 0, ci = 0, deleting = false;

  function tick(){
    const current = roles[ri];
    if(!deleting){
      ci++;
      el.textContent = current.slice(0, ci);
      if(ci === current.length){ deleting = true; setTimeout(tick, 1400); return; }
    } else {
      ci--;
      el.textContent = current.slice(0, ci);
      if(ci === 0){ deleting = false; ri = (ri+1) % roles.length; }
    }
    setTimeout(tick, deleting ? 35 : 65);
  }
  tick();
</script>

</body>
</html>
