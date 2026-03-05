<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Sudheer Mishra — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;500;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #21262d;
    --accent: #4230ff;
    --accent2: #00d4aa;
    --text: #e6edf3;
    --muted: #8b949e;
    --green: #3fb950;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Ubuntu', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── HERO BANNER ── */
  .hero-banner {
    width: 100%;
    position: relative;
    overflow: hidden;
    background: linear-gradient(135deg, #0d1117 0%, #1a1040 40%, #0d1117 100%);
    border-bottom: 1px solid var(--border);
    min-height: 220px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .hero-banner::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 80% at 20% 50%, rgba(66,48,255,0.18) 0%, transparent 70%),
      radial-gradient(ellipse 50% 60% at 80% 50%, rgba(0,212,170,0.10) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(66,48,255,0.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(66,48,255,0.06) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 2;
    text-align: center;
    padding: 2rem 1rem;
    width: 100%;
  }

  /* ── TYPING ANIMATION ── */
  .typing-wrapper {
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 70px;
  }

  .typing-text {
    font-family: 'Ubuntu', sans-serif;
    font-weight: 700;
    color: #E6F7E0;
    font-size: clamp(1.6rem, 5vw, 2.8rem);
    white-space: nowrap;
    overflow: hidden;
    border-right: 3px solid #E6F7E0;
    display: inline-block;
    max-width: 100%;
  }

  /* ── MAIN CONTAINER ── */
  .container {
    max-width: 960px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  /* ── INTRO SECTION ── */
  .intro-section {
    padding: 3rem 0 2rem;
  }

  .intro-grid {
    display: grid;
    grid-template-columns: 1fr 380px;
    gap: 2.5rem;
    align-items: start;
  }

  @media (max-width: 768px) {
    .intro-grid {
      grid-template-columns: 1fr;
    }
    .coding-img-wrap { order: -1; }
  }

  .subtitle {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    font-weight: 600;
    color: var(--accent2);
    margin-bottom: 1rem;
    letter-spacing: 0.02em;
  }

  .intro-text p {
    color: var(--muted);
    line-height: 1.8;
    margin-bottom: 1rem;
    font-size: clamp(0.875rem, 2vw, 0.95rem);
  }

  .intro-text p b {
    color: var(--text);
  }

  .coding-img-wrap {
    position: relative;
  }

  .coding-img-wrap img {
    width: 100%;
    max-width: 380px;
    border-radius: 12px;
    border: 1px solid var(--border);
    display: block;
    box-shadow: 0 8px 32px rgba(66,48,255,0.2);
  }

  /* ── ABOUT BULLETS ── */
  .about-list {
    list-style: none;
    margin-top: 1.5rem;
  }

  .about-list li {
    display: flex;
    align-items: flex-start;
    gap: 0.6rem;
    padding: 0.45rem 0;
    font-size: clamp(0.85rem, 2vw, 0.92rem);
    color: var(--muted);
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .about-list li:last-child { border-bottom: none; }

  .about-list .emoji {
    font-size: 1rem;
    flex-shrink: 0;
    margin-top: 0.1rem;
  }

  .about-list a { color: var(--accent2); text-decoration: none; }
  .about-list a:hover { text-decoration: underline; }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 2.5rem 0;
  }

  /* ── SECTION TITLES ── */
  .section-title {
    font-size: clamp(1.1rem, 3vw, 1.3rem);
    font-weight: 700;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
    margin-left: 0.5rem;
  }

  /* ── TECH GRID ── */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    justify-content: center;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.45rem 0.9rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 0.82rem;
    font-family: 'Fira Code', monospace;
    color: var(--text);
    transition: all 0.2s ease;
    cursor: default;
  }

  .tech-pill:hover {
    border-color: var(--accent);
    box-shadow: 0 0 12px rgba(66,48,255,0.3);
    transform: translateY(-2px);
    color: #fff;
  }

  .tech-pill .dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
  }

  /* ── CONNECT / SOCIAL ── */
  .social-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    justify-content: center;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.6rem 1.2rem;
    border-radius: 8px;
    font-size: 0.875rem;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.2s ease;
    border: 1px solid transparent;
  }

  .social-btn.linkedin {
    background: #0077B5;
    color: #fff;
  }
  .social-btn.instagram {
    background: linear-gradient(135deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
    color: #fff;
  }
  .social-btn.gmail {
    background: #D14836;
    color: #fff;
  }

  .social-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0,0,0,0.3);
    filter: brightness(1.1);
  }

  /* ── STATS BAR ── */
  .stats-bar {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;
    padding: 1.5rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    margin-bottom: 2.5rem;
  }

  .stat-item {
    text-align: center;
    flex: 1;
    min-width: 100px;
  }

  .stat-item .val {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--accent2);
    font-family: 'Fira Code', monospace;
  }

  .stat-item .lbl {
    font-size: 0.75rem;
    color: var(--muted);
    margin-top: 0.2rem;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 2rem 1rem;
    color: var(--muted);
    font-size: 0.8rem;
    border-top: 1px solid var(--border);
    margin-top: 2rem;
  }

  /* ── FADE IN ANIMATION ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .fade-up {
    opacity: 0;
    animation: fadeUp 0.6s ease forwards;
  }

  .fade-up:nth-child(1) { animation-delay: 0.1s; }
  .fade-up:nth-child(2) { animation-delay: 0.2s; }
  .fade-up:nth-child(3) { animation-delay: 0.3s; }
  .fade-up:nth-child(4) { animation-delay: 0.4s; }
  .fade-up:nth-child(5) { animation-delay: 0.5s; }
</style>
</head>
<body>

<!-- ── HERO BANNER ── -->
<div class="hero-banner">
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="typing-wrapper">
      <span class="typing-text" id="typingEl"></span>
    </div>
  </div>
</div>

<!-- ── MAIN CONTENT ── -->
<main class="container">

  <!-- INTRO -->
  <section class="intro-section">
    <div class="intro-grid">
      <div class="intro-text fade-up">
        <p class="subtitle">A passionate Full-Stack Web Developer based in India 🇮🇳</p>
        <p>
          I have a strong interest in building modern web applications and continuously improving my development skills.
          My main focus is <b>React and JavaScript</b>, and I also have working knowledge of
          <b>Node.js, Express, and MongoDB</b> for backend development.
        </p>
        <p>
          I enjoy learning by building real projects and exploring new technologies step by step.
          I believe consistent practice and curiosity are the best ways to grow as a developer,
          and I'm always working towards becoming a more complete full-stack engineer 🚀
        </p>

        <ul class="about-list">
          <li><span class="emoji">🌱</span> Currently learning and building Full-Stack Applications</li>
          <li><span class="emoji">🤝</span> Open to collaborate on real-world projects</li>
          <li><span class="emoji">👀</span> Love solving problems through code</li>
          <li><span class="emoji">📫</span> Reach me at: <a href="mailto:sudheermishra8587@gmail.com">sudheermishra8587@gmail.com</a></li>
          <li><span class="emoji">⚡</span> Fun fact: I learn best by building real projects</li>
        </ul>
      </div>

      <div class="coding-img-wrap fade-up">
        <img
          src="https://github.com/user-attachments/assets/83b1a90a-d77c-4fe6-b44a-93ff38dd26d4"
          alt="Coding illustration"
        />
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- STATS -->
  <div class="stats-bar fade-up">
    <div class="stat-item">
      <div class="val">1+</div>
      <div class="lbl">Years Learning</div>
    </div>
    <div class="stat-item">
      <div class="val">10+</div>
      <div class="lbl">Projects Built</div>
    </div>
    <div class="stat-item">
      <div class="val">5+</div>
      <div class="lbl">Technologies</div>
    </div>
    <div class="stat-item">
      <div class="val">∞</div>
      <div class="lbl">Curiosity</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <section class="fade-up">
    <h2 class="section-title">🛠️ Tools &amp; Technologies I Use</h2>
    <div class="tech-grid">
      <div class="tech-pill"><span class="dot" style="background:#e34c26"></span>HTML</div>
      <div class="tech-pill"><span class="dot" style="background:#264de4"></span>CSS</div>
      <div class="tech-pill"><span class="dot" style="background:#f7df1e"></span>JavaScript</div>
      <div class="tech-pill"><span class="dot" style="background:#61dafb"></span>React</div>
      <div class="tech-pill"><span class="dot" style="background:#3fb950"></span>Node.js</div>
      <div class="tech-pill"><span class="dot" style="background:#888"></span>Express</div>
      <div class="tech-pill"><span class="dot" style="background:#47a248"></span>MongoDB</div>
      <div class="tech-pill"><span class="dot" style="background:#f05032"></span>Git</div>
      <div class="tech-pill"><span class="dot" style="background:#fff"></span>GitHub</div>
      <div class="tech-pill"><span class="dot" style="background:#ef5b25"></span>Postman</div>
      <div class="tech-pill"><span class="dot" style="background:#007acc"></span>VS Code</div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- CONNECT -->
  <section class="fade-up">
    <h2 class="section-title">🌐 Connect with me</h2>
    <div class="social-row">
      <a href="https://www.linkedin.com/in/sudheer-mishra-b7302a258/" class="social-btn linkedin" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="https://www.instagram.com/thesudheermishra" class="social-btn instagram" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
        Instagram
      </a>
      <a href="mailto:sudheermishra8587@gmail.com" class="social-btn gmail">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
        Gmail
      </a>
    </div>
  </section>

</main>

<footer class="footer">
  Made with ❤️ by Sudheer Mishra &nbsp;·&nbsp; Full-Stack Developer 🇮🇳
</footer>

<script>
  // ── TYPING ANIMATION (fully responsive, no fixed width clipping) ──
  const lines = [
    "Hello 👋, I'm Sudheer 🙋",
    "Nice to Meet you 🙂"
  ];

  const el = document.getElementById('typingEl');
  let lineIdx = 0;
  let charIdx = 0;
  let deleting = false;
  let pauseCounter = 0;

  function type() {
    const current = lines[lineIdx];

    if (!deleting) {
      // typing forward
      charIdx++;
      el.textContent = current.slice(0, charIdx);

      if (charIdx === current.length) {
        // pause before deleting
        if (pauseCounter < 30) {
          pauseCounter++;
          setTimeout(type, 80);
          return;
        }
        pauseCounter = 0;
        deleting = true;
        setTimeout(type, 80);
        return;
      }
      setTimeout(type, 70);
    } else {
      // deleting
      charIdx--;
      el.textContent = current.slice(0, charIdx);

      if (charIdx === 0) {
        deleting = false;
        lineIdx = (lineIdx + 1) % lines.length;
        setTimeout(type, 400);
        return;
      }
      setTimeout(type, 40);
    }
  }

  // Start after short delay so page loads first
  setTimeout(type, 500);
</script>

</body>
</html>
