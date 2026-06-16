
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;700&display=swap');
  *{margin:0;padding:0;box-sizing:border-box;}
  :root{
    --ink:#0a0f1e;--ink2:#1a2035;--ink3:#243050;
    --cyan:#00d4ff;--purple:#a855f7;--green:#22d3a5;
    --text:#e2eaf6;--muted:#7a8bb0;
    --card:#111827;--card2:#1e2a3a;
  }
  body{background:var(--ink);color:var(--text);font-family:'Space Grotesk',sans-serif;overflow-x:hidden;}

  .profile{width:100%;min-height:100vh;background:var(--ink);perspective:1200px;}

  /* ── HERO ── */
  .hero{position:relative;width:100%;height:380px;display:flex;align-items:center;justify-content:center;overflow:hidden;}
  .hero-bg{position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 0%,#1a1060 0%,#0a0f1e 70%);}
  .grid-lines{position:absolute;inset:0;background-image:linear-gradient(rgba(0,212,255,.06) 1px,transparent 1px),linear-gradient(90deg,rgba(0,212,255,.06) 1px,transparent 1px);background-size:40px 40px;animation:gridPan 20s linear infinite;}
  @keyframes gridPan{from{background-position:0 0}to{background-position:40px 40px}}

  /* Floating orbs */
  .orb{position:absolute;border-radius:50%;filter:blur(60px);animation:orbFloat 8s ease-in-out infinite;}
  .orb1{width:300px;height:300px;background:rgba(168,85,247,.15);top:-80px;left:-60px;animation-delay:0s;}
  .orb2{width:240px;height:240px;background:rgba(0,212,255,.12);bottom:-60px;right:-40px;animation-delay:3s;}
  .orb3{width:180px;height:180px;background:rgba(34,211,165,.1);top:30%;right:20%;animation-delay:5s;}
  @keyframes orbFloat{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-20px) scale(1.05)}}

  .hero-content{position:relative;z-index:2;text-align:center;}
  .avatar-ring{width:100px;height:100px;border-radius:50%;margin:0 auto 20px;position:relative;animation:avatarPulse 3s ease-in-out infinite;}
  .avatar-ring::before{content:'';position:absolute;inset:-3px;border-radius:50%;background:conic-gradient(from 0deg,#00d4ff,#a855f7,#22d3a5,#00d4ff);animation:spin 4s linear infinite;}
  .avatar-inner{position:absolute;inset:3px;border-radius:50%;background:linear-gradient(135deg,#1e2a3a,#0a0f1e);display:flex;align-items:center;justify-content:center;font-family:'JetBrains Mono',monospace;font-size:32px;font-weight:700;color:var(--cyan);}
  @keyframes spin{to{transform:rotate(360deg)}}
  @keyframes avatarPulse{0%,100%{transform:scale(1)}50%{transform:scale(1.03)}}

  .hero-name{font-size:clamp(28px,5vw,52px);font-weight:700;letter-spacing:-1px;line-height:1.1;margin-bottom:8px;}
  .hero-name span{background:linear-gradient(90deg,#00d4ff,#a855f7,#22d3a5);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
  .hero-roles{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-bottom:20px;}
  .role-pill{padding:4px 14px;border-radius:20px;font-size:12px;font-weight:500;border:1px solid;animation:pillGlow 3s ease-in-out infinite;}
  .role-pill:nth-child(1){color:var(--cyan);border-color:rgba(0,212,255,.4);background:rgba(0,212,255,.08);animation-delay:0s;}
  .role-pill:nth-child(2){color:var(--purple);border-color:rgba(168,85,247,.4);background:rgba(168,85,247,.08);animation-delay:1s;}
  .role-pill:nth-child(3){color:var(--green);border-color:rgba(34,211,165,.4);background:rgba(34,211,165,.08);animation-delay:2s;}
  @keyframes pillGlow{0%,100%{box-shadow:none}50%{box-shadow:0 0 12px currentColor}}

  /* Typing text */
  .typing-wrap{height:28px;display:flex;align-items:center;justify-content:center;gap:6px;}
  .typing-text{font-family:'JetBrains Mono',monospace;font-size:14px;color:var(--cyan);overflow:hidden;white-space:nowrap;border-right:2px solid var(--cyan);animation:typing 12s steps(30) infinite,blink .7s step-end infinite;}
  @keyframes typing{
    0%{width:0;content:''}
    8%{width:12ch}10%,25%{width:12ch}
    30%{width:0}33%,48%{width:0}
    40%{width:18ch}50%,65%{width:18ch}
    70%{width:0}75%,90%{width:0}
    80%{width:20ch}100%{width:20ch}
  }
  @keyframes blink{50%{border-color:transparent}}
  .prompt{font-family:'JetBrains Mono',monospace;font-size:14px;color:var(--green);}

  /* Social links */
  .social-row{display:flex;gap:10px;justify-content:center;margin-top:16px;}
  .social-btn{display:flex;align-items:center;gap:6px;padding:7px 16px;border-radius:8px;font-size:13px;font-weight:500;text-decoration:none;border:1px solid;transition:all .2s;cursor:pointer;}
  .social-btn.li{color:#0077b5;border-color:rgba(0,119,181,.4);background:rgba(0,119,181,.08);}
  .social-btn.li:hover{background:rgba(0,119,181,.2);}
  .social-btn.gm{color:#ea4335;border-color:rgba(234,67,53,.4);background:rgba(234,67,53,.08);}
  .social-btn.gm:hover{background:rgba(234,67,53,.2);}
  .social-btn.lc{color:#ffa116;border-color:rgba(255,161,22,.4);background:rgba(255,161,22,.08);}
  .social-btn.lc:hover{background:rgba(255,161,22,.2);}
  .social-icon{width:16px;height:16px;border-radius:3px;}

  /* ── SECTIONS ── */
  .section{width:100%;padding:40px 32px;}
  .section-label{font-size:11px;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--muted);margin-bottom:6px;}
  .section-title{font-size:22px;font-weight:700;margin-bottom:24px;}
  .section-title span{background:linear-gradient(90deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}

  /* ── ABOUT 2-col ── */
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
  @media(max-width:600px){.about-grid{grid-template-columns:1fr;}}
  .info-card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:20px;position:relative;overflow:hidden;transition:transform .2s,border-color .2s;}
  .info-card::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(0,212,255,.04),transparent);pointer-events:none;}
  .info-card:hover{transform:translateY(-3px);border-color:rgba(0,212,255,.25);}
  .info-card-title{font-size:13px;font-weight:600;color:var(--cyan);margin-bottom:12px;display:flex;align-items:center;gap:6px;}
  .info-list{display:flex;flex-direction:column;gap:7px;}
  .info-item{font-size:13px;color:var(--muted);display:flex;align-items:center;gap:8px;}
  .info-item::before{content:'';width:4px;height:4px;border-radius:50%;background:var(--cyan);flex-shrink:0;}

  /* ── TECH STACK ── */
  .tech-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(90px,1fr));gap:12px;}
  .tech-card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:12px;padding:14px 10px;display:flex;flex-direction:column;align-items:center;gap:8px;transition:all .25s;position:relative;overflow:hidden;cursor:default;}
  .tech-card:hover{transform:translateY(-5px) rotateX(8deg);border-color:rgba(0,212,255,.3);box-shadow:0 12px 30px rgba(0,212,255,.12);}
  .tech-icon{width:32px;height:32px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:18px;}
  .tech-name{font-size:11px;font-weight:500;color:var(--muted);text-align:center;}

  /* ── STATS ── */
  .stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:14px;}
  .stat-card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:20px;text-align:center;position:relative;overflow:hidden;transition:transform .2s;}
  .stat-card:hover{transform:scale(1.03);}
  .stat-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;}
  .stat-card.c1::after{background:linear-gradient(90deg,var(--cyan),transparent);}
  .stat-card.c2::after{background:linear-gradient(90deg,var(--purple),transparent);}
  .stat-card.c3::after{background:linear-gradient(90deg,var(--green),transparent);}
  .stat-card.c4::after{background:linear-gradient(90deg,#f59e0b,transparent);}
  .stat-num{font-size:32px;font-weight:700;font-family:'JetBrains Mono',monospace;margin-bottom:4px;}
  .stat-card.c1 .stat-num{color:var(--cyan);}
  .stat-card.c2 .stat-num{color:var(--purple);}
  .stat-card.c3 .stat-num{color:var(--green);}
  .stat-card.c4 .stat-num{color:#f59e0b;}
  .stat-label{font-size:12px;color:var(--muted);}

  /* ── PROJECTS ── */
  .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px;}
  .project-card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:20px;transition:all .3s;position:relative;overflow:hidden;cursor:pointer;}
  .project-card::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;opacity:0;transition:opacity .3s;}
  .project-card:hover{transform:translateY(-6px);}
  .project-card:hover::before{opacity:1;}
  .project-card.p1::before{background:linear-gradient(90deg,transparent,var(--cyan),transparent);}
  .project-card.p2::before{background:linear-gradient(90deg,transparent,var(--purple),transparent);}
  .project-card.p3::before{background:linear-gradient(90deg,transparent,var(--green),transparent);}
  .project-card:hover.p1{border-color:rgba(0,212,255,.3);box-shadow:0 16px 40px rgba(0,212,255,.08);}
  .project-card:hover.p2{border-color:rgba(168,85,247,.3);box-shadow:0 16px 40px rgba(168,85,247,.08);}
  .project-card:hover.p3{border-color:rgba(34,211,165,.3);box-shadow:0 16px 40px rgba(34,211,165,.08);}
  .project-emoji{font-size:28px;margin-bottom:10px;}
  .project-name{font-size:15px;font-weight:600;margin-bottom:6px;}
  .project-desc{font-size:12px;color:var(--muted);line-height:1.5;margin-bottom:12px;}
  .project-tags{display:flex;flex-wrap:wrap;gap:6px;}
  .tag{font-size:10px;padding:3px 8px;border-radius:6px;font-weight:500;}
  .tag-cyan{background:rgba(0,212,255,.1);color:var(--cyan);}
  .tag-purple{background:rgba(168,85,247,.1);color:var(--purple);}
  .tag-green{background:rgba(34,211,165,.1);color:var(--green);}

  /* ── GOALS ── */
  .goals-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px;}
  .goal-card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:12px;padding:16px;display:flex;align-items:center;gap:10px;transition:border-color .2s;}
  .goal-card:hover{border-color:rgba(168,85,247,.3);}
  .goal-dot{width:8px;height:8px;border-radius:50%;background:var(--purple);flex-shrink:0;}
  .goal-text{font-size:13px;color:var(--muted);}

  /* ── GITHUB EMBED ── */
  .github-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px;}
  @media(max-width:560px){.github-grid{grid-template-columns:1fr;}}
  .github-img-wrap{border-radius:12px;overflow:hidden;border:1px solid rgba(255,255,255,.06);background:var(--card);}
  .github-img-wrap img{width:100%;display:block;}

  /* ── FOOTER ── */
  .footer{width:100%;padding:30px 32px;display:flex;align-items:center;justify-content:space-between;border-top:1px solid rgba(255,255,255,.06);}
  .footer-left{font-size:12px;color:var(--muted);font-family:'JetBrains Mono',monospace;}
  .views-badge{display:flex;align-items:center;gap:8px;font-size:12px;color:var(--muted);}
  .views-dot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 2s ease-in-out infinite;}
  @keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(1.5)}}

  /* ── DIVIDER ── */
  .divider{width:100%;height:1px;background:linear-gradient(90deg,transparent,rgba(0,212,255,.2),rgba(168,85,247,.2),transparent);margin:0 32px;width:calc(100% - 64px);}

  /* ── PARTICLE DOTS ── */
  .particles{position:absolute;inset:0;pointer-events:none;overflow:hidden;}
  .particle{position:absolute;width:2px;height:2px;border-radius:50%;background:var(--cyan);opacity:0;animation:particleFly var(--dur,8s) var(--delay,0s) ease-in-out infinite;}
  @keyframes particleFly{0%{transform:translateY(100%) translateX(0);opacity:0}20%{opacity:.6}80%{opacity:.3}100%{transform:translateY(-200px) translateX(var(--drift,20px));opacity:0}}

  /* ── 3D TILT on hover (JS applied) ── */
  .tilt3d{transform-style:preserve-3d;transition:transform .15s ease;}
</style>

<div class="profile" role="main" aria-label="Raushan Kumar GitHub Profile">
  <h2 class="sr-only">Raushan Kumar — Java Developer GitHub Profile</h2>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>
    <div class="grid-lines"></div>
    <!-- particles -->
    <div class="particles" id="particles"></div>
    <div class="hero-content">
      <div class="avatar-ring">
        <div class="avatar-inner">RK</div>
      </div>
      <div class="hero-name"><span>Raushan Kumar</span></div>
      <div class="hero-roles">
        <span class="role-pill">Java Developer</span>
        <span class="role-pill">Problem Solver</span>
        <span class="role-pill">Backend Enthusiast</span>
      </div>
      <div class="typing-wrap">
        <span class="prompt">$</span>
        <span class="typing-text" id="typer">Solving DSA...</span>
      </div>
      <div class="social-row">
        <a class="social-btn li" href="https://www.linkedin.com/in/raushan-kumar-189472307/" target="_blank">
          <svg class="social-icon" viewBox="0 0 24 24" fill="#0077b5"><path d="M20 3H4a1 1 0 0 0-1 1v16a1 1 0 0 0 1 1h16a1 1 0 0 0 1-1V4a1 1 0 0 0-1-1zM8.339 18.337H5.667v-8.59h2.672v8.59zM7.003 8.574a1.548 1.548 0 1 1 0-3.096 1.548 1.548 0 0 1 0 3.096zm11.335 9.763h-2.669V14.16c0-.996-.018-2.277-1.388-2.277-1.39 0-1.601 1.086-1.601 2.207v4.248h-2.667v-8.59h2.56v1.174h.037c.355-.675 1.227-1.387 2.524-1.387 2.704 0 3.203 1.778 3.203 4.092v4.71z"/></svg>
          LinkedIn
        </a>
        <a class="social-btn gm" href="mailto:shahraushan26@gmail.com">
          <svg class="social-icon" viewBox="0 0 24 24" fill="#ea4335"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
          Gmail
        </a>
        <a class="social-btn lc" href="https://leetcode.com/u/Raushanshah07/" target="_blank">
          <svg class="social-icon" viewBox="0 0 24 24" fill="#ffa116"><path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z"/></svg>
          LeetCode
        </a>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-label">by the numbers</div>
    <div class="section-title"><span>At a Glance</span></div>
    <div class="stats-grid">
      <div class="stat-card c1">
        <div class="stat-num" id="cnt-leet">0</div>
        <div class="stat-label">LeetCode Problems</div>
      </div>
      <div class="stat-card c2">
        <div class="stat-num" id="cnt-repos">0</div>
        <div class="stat-label">GitHub Repos</div>
      </div>
      <div class="stat-card c3">
        <div class="stat-num" id="cnt-streak">0</div>
        <div class="stat-label">Day Streak</div>
      </div>
      <div class="stat-card c4">
        <div class="stat-num" id="cnt-proj">0</div>
        <div class="stat-label">Projects Built</div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-label">who i am</div>
    <div class="section-title"><span>About Me</span></div>
    <div class="about-grid">
      <div class="info-card tilt3d">
        <div class="info-card-title">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
          Currently focused on
        </div>
        <div class="info-list">
          <div class="info-item">Computer Science Student</div>
          <div class="info-item">Backend Developer</div>
          <div class="info-item">Solving DSA problems daily</div>
          <div class="info-item">500+ LeetCode goal in 2025</div>
        </div>
      </div>
      <div class="info-card tilt3d">
        <div class="info-card-title">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
          Learning stack
        </div>
        <div class="info-list">
          <div class="info-item">Spring Boot & REST APIs</div>
          <div class="info-item">System Design</div>
          <div class="info-item">Docker & AWS</div>
          <div class="info-item">Full Stack Projects</div>
        </div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-label">tools & technologies</div>
    <div class="section-title"><span>Tech Stack</span></div>
    <div class="tech-grid" id="tech-grid"></div>
  </div>

  <div class="divider"></div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-label">what i've built</div>
    <div class="section-title"><span>Featured Projects</span></div>
    <div class="projects-grid">
      <div class="project-card p1 tilt3d">
        <div class="project-emoji">💰</div>
        <div class="project-name">EXPENSPHER</div>
        <div class="project-desc">Personal finance tracker to monitor income, expenses and savings with clean dashboards.</div>
        <div class="project-tags">
          <span class="tag tag-green">Node.js</span>
          <span class="tag tag-green">MongoDB</span>
          <span class="tag tag-green">Express</span>
        </div>
      </div>
      <div class="project-card p2 tilt3d">
        <div class="project-emoji">🎮</div>
        <div class="project-name">Simon Says</div>
        <div class="project-desc">Classic memory game with increasing difficulty, smooth animations, and score tracking.</div>
        <div class="project-tags">
          <span class="tag tag-cyan">HTML</span>
          <span class="tag tag-cyan">CSS</span>
          <span class="tag tag-cyan">JavaScript</span>
        </div>
      </div>
      <div class="project-card p3 tilt3d">
        <div class="project-emoji">🌐</div>
        <div class="project-name">Portfolio</div>
        <div class="project-desc">Personal website showcasing projects, skills and experience with fully responsive design.</div>
        <div class="project-tags">
          <span class="tag tag-purple">Responsive</span>
          <span class="tag tag-purple">Web Design</span>
        </div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-label">github activity</div>
    <div class="section-title"><span>GitHub Analytics</span></div>
    <div class="github-grid">
      <div class="github-img-wrap">
        <img src="https://github-readme-stats.vercel.app/api?username=raushankumar018&show_icons=true&theme=tokyonight&hide_border=true&bg_color=111827&title_color=00d4ff&text_color=7a8bb0&icon_color=a855f7" alt="GitHub Stats" loading="lazy"/>
      </div>
      <div class="github-img-wrap">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=raushankumar018&theme=tokyonight&hide_border=true&background=111827&currStreakLabelColor=00d4ff&sideLabels=7a8bb0" alt="GitHub Streak" loading="lazy"/>
      </div>
    </div>
    <div style="display:flex;justify-content:center;">
      <div class="github-img-wrap" style="max-width:420px;width:100%;">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=raushankumar018&layout=compact&theme=tokyonight&hide_border=true&bg_color=111827&title_color=00d4ff&text_color=7a8bb0" alt="Top Languages" loading="lazy"/>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- GOALS -->
  <div class="section">
    <div class="section-label">the mission</div>
    <div class="section-title"><span>2025 Goals</span></div>
    <div class="goals-grid">
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">500+ LeetCode problems</div></div>
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">Build full stack projects</div></div>
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">Crack SDE role</div></div>
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">Contribute to open source</div></div>
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">Master system design</div></div>
      <div class="goal-card"><div class="goal-dot"></div><div class="goal-text">Deploy on AWS + Docker</div></div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-left">// raushankumar018 · built with ❤ + code</div>
    <div class="views-badge">
      <div class="views-dot"></div>
      <span>Profile live</span>
    </div>
  </div>
</div>

<script>
/* Particles */
(function(){
  const p=document.getElementById('particles');
  for(let i=0;i<18;i++){
    const d=document.createElement('div');
    d.className='particle';
    d.style.cssText=`left:${Math.random()*100}%;--dur:${6+Math.random()*8}s;--delay:${Math.random()*8}s;--drift:${(Math.random()-.5)*80}px;opacity:0;`;
    p.appendChild(d);
  }
})();

/* Typing */
const lines=['Solving DSA...','Building APIs...','Crafting backends...','Pushing to GitHub...'];
let li=0,ci=0,del=false;
const el=document.getElementById('typer');
function tick(){
  const t=lines[li];
  if(!del){el.textContent=t.slice(0,++ci);if(ci===t.length){del=true;setTimeout(tick,1400);return;}}
  else{el.textContent=t.slice(0,--ci);if(ci===0){del=false;li=(li+1)%lines.length;}}
  setTimeout(tick,del?60:90);
}
tick();

/* Counters */
function animCount(id,target,dur=1400){
  const el=document.getElementById(id);
  const start=performance.now();
  function step(now){
    const p=Math.min((now-start)/dur,1);
    el.textContent=Math.round(p*p*target)+(p<1?'':'');
    if(p<1)requestAnimationFrame(step);
    else el.textContent=target+(id==='cnt-leet'?'+':'');
  }
  requestAnimationFrame(step);
}
const obs=new IntersectionObserver(e=>{if(e[0].isIntersecting){animCount('cnt-leet',350);animCount('cnt-repos',12);animCount('cnt-streak',45);animCount('cnt-proj',8);obs.disconnect();}},{threshold:.3});
obs.observe(document.querySelector('.stats-grid'));

/* Tech cards */
const techs=[
  {n:'Java',c:'#ea8600',bg:'rgba(234,134,0,.12)',svg:'<svg viewBox="0 0 24 24" fill="#ea8600" width="20" height="20"><path d="M8.851 18.56s-.917.534.653.714c1.902.218 2.874.187 4.969-.211 0 0 .552.346 1.321.646-4.699 2.013-10.633-.118-6.943-1.149M8.276 15.933s-1.028.761.542.924c2.032.209 3.636.227 6.413-.308 0 0 .384.389.987.602-5.679 1.661-12.007.13-7.942-1.218M13.116 11.475c1.158 1.333-.304 2.533-.304 2.533s2.939-1.518 1.589-3.418c-1.261-1.772-2.228-2.652 3.007-5.688 0-.001-8.216 2.051-4.292 6.573M19.33 20.504s.679.559-.747.991c-2.712.822-11.288 1.069-13.669.033-.856-.373.75-.89 1.254-.998.527-.114.828-.093.828-.093-.953-.671-6.156 1.317-2.643 1.887 9.58 1.553 17.462-.7 14.977-1.82M9.292 13.21s-4.362 1.036-1.544 1.412c1.189.159 3.561.123 5.77-.062 1.806-.152 3.618-.477 3.618-.477s-.637.272-1.098.587c-4.429 1.165-12.986.623-10.522-.568 2.082-1.006 3.776-.892 3.776-.892M17.116 17.584c4.503-2.34 2.421-4.589.968-4.285-.355.074-.515.138-.515.138s.132-.207.385-.297c2.875-1.011 5.086 2.981-.928 4.562 0-.001.07-.062.09-.118M14.401 0s2.494 2.494-2.365 6.33c-3.896 3.077-.888 4.832-.001 6.836-2.274-2.053-3.943-3.858-2.824-5.539 1.644-2.469 6.197-3.665 5.19-7.627M9.734 23.924c4.322.277 10.959-.153 11.116-2.198 0 0-.302.775-3.572 1.391-3.688.694-8.239.613-10.937.168 0-.001.553.457 3.393.639"/></svg>'},
  {n:'Spring',c:'#6db33f',bg:'rgba(109,179,63,.12)',svg:'<svg viewBox="0 0 24 24" fill="#6db33f" width="20" height="20"><path d="M21.8537 1.4158a10.4504 10.4504 0 0 1-1.284 2.2471A11.9666 11.9666 0 0 0 12.2301 0C5.4948 0 0 5.4948 0 12.2301c0 6.7353 5.4948 12.2301 12.2301 12.2301 6.7353 0 12.2301-5.4948 12.2301-12.2301 0-3.1143-.6744-6.0737-1.7958-8.5786zm-9.6236 18.1a7.1944 7.1944 0 0 1-5.0468-2.0614 7.1944 7.1944 0 0 1-2.0614-5.0468 7.1944 7.1944 0 0 1 2.0614-5.0468 7.1944 7.1944 0 0 1 5.0468-2.0614 7.1944 7.1944 0 0 1 5.0468 2.0614 7.1944 7.1944 0 0 1 2.0614 5.0468 7.1944 7.1944 0 0 1-2.0614 5.0468A7.1944 7.1944 0 0 1 12.2301 19.5158z"/></svg>'},
  {n:'MySQL',c:'#4479a1',bg:'rgba(68,121,161,.12)',svg:'<svg viewBox="0 0 24 24" fill="#4479a1" width="20" height="20"><path d="M16.405 5.501c-.115 0-.193.014-.274.033v.013h.014c.054.104.146.18.214.273.054.107.1.214.154.32l.014-.015c.094-.066.14-.172.14-.333-.04-.047-.046-.094-.08-.14-.04-.067-.126-.1-.182-.151zM5.77 18.695h-.927a50.854 50.854 0 0 0-.27-4.41h-.008l-1.41 4.41H2.45l-1.4-4.41h-.01a72.892 72.892 0 0 0-.195 4.41H0c.055-1.966.192-3.81.41-5.55h1.15l1.335 4.064h.008l1.347-4.064h1.095c.242 2.015.384 3.86.428 5.55zm4.017-4.08c-.378 2.045-.876 3.533-1.492 4.46-.482.716-1.01 1.073-1.583 1.073-.153 0-.34-.046-.566-.138v-.494c.11.017.24.026.386.026.268 0 .483-.075.647-.222.197-.18.295-.382.295-.605 0-.155-.077-.47-.23-.944L6.23 14.615h.91l.727 3.01c.164.664.billy .664.5 0 .5 0l.878-3.011h.872zm0 0"/></svg>'},
  {n:'MongoDB',c:'#47a248',bg:'rgba(71,162,72,.12)',svg:'<svg viewBox="0 0 24 24" fill="#47a248" width="20" height="20"><path d="M17.193 9.555c-1.264-5.58-4.252-7.414-4.573-8.115-.28-.394-.53-.954-.735-1.44-.036.495-.055.685-.523 1.184-.723.566-4.438 3.682-4.74 10.02-.282 5.912 4.27 9.435 4.888 9.884l.07.05A73.49 73.49 0 0 1 11.91 24h.481c.114-1.032.284-2.056.51-3.07.417-.296.604-.463.85-.693a11.342 11.342 0 0 0 3.639-8.464c.01-.814-.103-1.662-.197-2.218zm-5.336 8.195s0-8.291.275-8.29c.213 0 .49 10.695.49 10.695-.381-.045-.765-1.76-.765-2.405z"/></svg>'},
  {n:'Node.js',c:'#339933',bg:'rgba(51,153,51,.12)',svg:'<svg viewBox="0 0 24 24" fill="#339933" width="20" height="20"><path d="M11.998.016C5.368.016.044 5.34.044 11.97c0 6.63 5.324 11.955 11.954 11.955 6.63 0 11.955-5.325 11.955-11.955C23.953 5.34 18.628.016 11.998.016zM6.235 17.992a.517.517 0 0 1-.517-.517V6.525a.52.52 0 0 1 .52-.52.52.52 0 0 1 .52.52v7.68l3.604-2.08a.516.516 0 0 1 .703.19.517.517 0 0 1-.19.703l-4.64 2.678zm5.726 0a.517.517 0 0 1-.517-.517v-4.808c0-1.93 1.042-3.718 2.722-4.678a5.41 5.41 0 0 1 5.407 0 5.41 5.41 0 0 1 2.723 4.678.517.517 0 0 1-.517.517.517.517 0 0 1-.517-.517c0-1.545-.833-2.974-2.178-3.745a4.375 4.375 0 0 0-4.37 0 4.375 4.375 0 0 0-2.186 3.745v4.808a.517.517 0 0 1-.517.517z"/></svg>'},
  {n:'Docker',c:'#2496ed',bg:'rgba(36,150,237,.12)',svg:'<svg viewBox="0 0 24 24" fill="#2496ed" width="20" height="20"><path d="M13.983 11.078h2.119a.186.186 0 0 0 .186-.185V9.006a.186.186 0 0 0-.186-.186h-2.119a.185.185 0 0 0-.185.185v1.888c0 .102.083.185.185.185m-2.954-5.43h2.118a.186.186 0 0 0 .186-.186V3.574a.186.186 0 0 0-.186-.185h-2.118a.185.185 0 0 0-.185.185v1.888c0 .102.082.185.185.185m0 2.716h2.118a.187.187 0 0 0 .186-.186V6.29a.186.186 0 0 0-.186-.185h-2.118a.185.185 0 0 0-.185.185v1.887c0 .102.082.185.185.186m-2.93 0h2.12a.186.186 0 0 0 .184-.186V6.29a.185.185 0 0 0-.185-.185H8.1a.185.185 0 0 0-.185.185v1.887c0 .102.083.185.185.186m-2.964 0h2.119a.186.186 0 0 0 .185-.186V6.29a.185.185 0 0 0-.185-.185H5.136a.186.186 0 0 0-.186.185v1.887c0 .102.084.185.186.186m5.893 2.715h2.118a.186.186 0 0 0 .186-.185V9.006a.186.186 0 0 0-.186-.186h-2.118a.185.185 0 0 0-.185.185v1.888c0 .102.082.185.185.185m-2.93 0h2.12a.185.185 0 0 0 .184-.185V9.006a.185.185 0 0 0-.184-.186h-2.12a.185.185 0 0 0-.185.185v1.888c0 .102.083.185.185.185m-2.964 0h2.119a.185.185 0 0 0 .185-.185V9.006a.185.185 0 0 0-.184-.186h-2.12a.186.186 0 0 0-.186.186v1.887c0 .102.084.185.186.185m-2.92 0h2.12a.185.185 0 0 0 .184-.185V9.006a.185.185 0 0 0-.184-.186h-2.12a.185.185 0 0 0-.185.185v1.888c0 .102.083.185.185.185M23.763 9.89c-.065-.051-.672-.51-1.954-.51-.338.001-.676.03-1.01.087-.248-1.7-1.653-2.53-1.716-2.566l-.344-.199-.226.327c-.284.438-.49.922-.612 1.43-.23.97-.09 1.882.403 2.661-.595.332-1.55.413-1.744.42H.751a.751.751 0 0 0-.75.748 11.376 11.376 0 0 0 .692 4.062c.545 1.428 1.355 2.48 2.41 3.124 1.18.723 3.1 1.137 5.275 1.137.983.003 1.963-.086 2.93-.266a12.248 12.248 0 0 0 3.823-1.389c.98-.567 1.86-1.288 2.61-2.136 1.252-1.418 1.998-2.997 2.553-4.4h.221c1.372 0 2.215-.549 2.68-1.009.309-.293.55-.65.707-1.046l.098-.288Z"/></svg>'},
  {n:'Git',c:'#f05032',bg:'rgba(240,80,50,.12)',svg:'<svg viewBox="0 0 24 24" fill="#f05032" width="20" height="20"><path d="M23.546 10.93L13.067.452c-.604-.603-1.582-.603-2.188 0L8.708 2.627l2.76 2.76c.645-.215 1.379-.07 1.889.441.516.515.658 1.258.438 1.9l2.658 2.66c.645-.223 1.387-.078 1.9.435.721.72.721 1.884 0 2.604-.719.719-1.881.719-2.6 0-.539-.541-.674-1.337-.404-1.996L12.86 8.955v6.525c.176.086.342.203.488.348.713.721.713 1.883 0 2.6-.719.721-1.889.721-2.609 0-.719-.719-.719-1.879 0-2.598.182-.18.387-.316.605-.406V8.835c-.217-.091-.424-.222-.6-.401-.545-.545-.676-1.342-.396-2.009L7.636 3.7.45 10.881c-.6.605-.6 1.584 0 2.189l10.48 10.477c.604.604 1.582.604 2.186 0l10.43-10.43c.605-.603.605-1.582 0-2.187"/></svg>'},
  {n:'GitHub',c:'#ccc',bg:'rgba(200,200,200,.08)',svg:'<svg viewBox="0 0 24 24" fill="#ccc" width="20" height="20"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>'},
  {n:'HTML',c:'#e34f26',bg:'rgba(227,79,38,.12)',svg:'<svg viewBox="0 0 24 24" fill="#e34f26" width="20" height="20"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm7.031 9.75l-.232-2.718 10.059.003.23-2.622L5.412 4.41l.698 8.01h9.126l-.326 3.426-2.91.804-2.955-.81-.188-2.11H6.248l.33 4.171L12 19.351l5.379-1.443.744-8.157H8.531z"/></svg>'},
  {n:'CSS',c:'#1572b6',bg:'rgba(21,114,182,.12)',svg:'<svg viewBox="0 0 24 24" fill="#1572b6" width="20" height="20"><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.565-2.438L1.5 0zm17.09 4.413L5.41 4.41l.213 2.622 10.125.002-.255 2.716h-6.64l.24 2.573h6.182l-.366 3.523-2.91.804-2.956-.81-.188-2.11h-2.61l.29 3.855L12 19.288l5.373-1.53L18.59 4.414z"/></svg>'},
  {n:'Postman',c:'#ff6c37',bg:'rgba(255,108,55,.12)',svg:'<svg viewBox="0 0 24 24" fill="#ff6c37" width="20" height="20"><path d="M13.527.099C6.955-.744.942 3.9.099 10.473c-.843 6.572 3.8 12.584 10.373 13.428 6.573.843 12.587-3.801 13.428-10.374C24.744 6.955 20.101.943 13.527.099zm2.471 7.485a.855.855 0 0 0-.593.25l-4.453 4.453-.307-.307-.643-.643c4.389-4.376 5.18-4.418 5.996-3.753zm-4.863 4.861l4.44-4.44a.62.62 0 1 1 .877.877l-4.44 4.441-.877-.878zm-1.658 1.664l-.436.014-.878-.877.014-.437 1.3 1.3zm7.632-6.951c-.651-.562-1.886-.826-4.248 1.513l-.547-.547c2.661-2.663 4.457-2.145 5.055-1.509a6.313 6.313 0 0 0-.26.543z"/></svg>'},
  {n:'VS Code',c:'#007acc',bg:'rgba(0,122,204,.12)',svg:'<svg viewBox="0 0 24 24" fill="#007acc" width="20" height="20"><path d="M23.15 2.587L18.21.21a1.494 1.494 0 0 0-1.705.29l-9.46 8.63-4.12-3.128a.999.999 0 0 0-1.276.057L.327 7.261A1 1 0 0 0 .326 8.74L3.899 12 .326 15.26a1 1 0 0 0 .001 1.479L1.65 17.94a.999.999 0 0 0 1.276.057l4.12-3.128 9.46 8.63a1.492 1.492 0 0 0 1.704.29l4.942-2.377A1.5 1.5 0 0 0 24 19.06V4.94a1.5 1.5 0 0 0-.85-1.353zm-5.146 14.861L10.826 12l7.178-5.448v10.896z"/></svg>'},
];

const tg=document.getElementById('tech-grid');
techs.forEach(t=>{
  const c=document.createElement('div');
  c.className='tech-card tilt3d';
  c.innerHTML=`<div class="tech-icon" style="background:${t.bg}">${t.svg}</div><div class="tech-name">${t.n}</div>`;
  tg.appendChild(c);
});

/* 3D tilt effect */
document.querySelectorAll('.tilt3d').forEach(el=>{
  el.addEventListener('mousemove',e=>{
    const r=el.getBoundingClientRect();
    const x=(e.clientX-r.left)/r.width-.5;
    const y=(e.clientY-r.top)/r.height-.5;
    el.style.transform=`perspective(600px) rotateY(${x*14}deg) rotateX(${-y*14}deg) translateZ(6px)`;
  });
  el.addEventListener('mouseleave',()=>{
    el.style.transform='perspective(600px) rotateY(0) rotateX(0) translateZ(0)';
  });
});
</script>
