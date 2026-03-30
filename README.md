
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chad Lock</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --sand: #F2EAD3;
    --terra: #C4622D;
    --rust: #8B3A1F;
    --dust: #D4C4A8;
    --ink: #1E1208;
    --sage: #7A8C6E;
    --sky: #A8BDD1;
    --cream: #FAF6EE;
  }

  body {
    font-family: 'Inter', sans-serif;
    background-color: var(--cream);
    color: var(--ink);
    line-height: 1.6;
  }

  /* NAV */
  nav {
    background: var(--ink);
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  nav .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: var(--sand);
    letter-spacing: 0.05em;
  }
  nav .nav-links a {
    color: var(--dust);
    text-decoration: none;
    font-size: 0.8rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-left: 2rem;
    transition: color 0.2s;
  }
  nav .nav-links a:hover { color: var(--terra); }

  /* HERO */
  .hero {
    background: var(--sand);
    min-height: 90vh;
    display: flex;
    align-items: center;
    padding: 4rem 2rem;
    position: relative;
    overflow: hidden;
  }
  .hero-texture {
    position: absolute;
    inset: 0;
    opacity: 0.06;
    background-image: repeating-linear-gradient(
      45deg,
      var(--rust) 0px, var(--rust) 1px,
      transparent 1px, transparent 8px
    );
  }
  .hero-content {
    max-width: 900px;
    margin: 0 auto;
    position: relative;
    z-index: 1;
  }
  .eyebrow {
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--terra);
    margin-bottom: 1.5rem;
    font-weight: 500;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 8vw, 6rem);
    font-weight: 700;
    line-height: 1.05;
    color: var(--ink);
    margin-bottom: 1.5rem;
  }
  .hero h1 .accent {
    color: var(--terra);
    display: block;
  }
  .hero-tagline {
    font-size: 1.1rem;
    color: #5a4a38;
    max-width: 520px;
    margin-bottom: 2.5rem;
    font-weight: 300;
    line-height: 1.8;
  }
  .hero-cta {
    display: inline-block;
    background: var(--terra);
    color: var(--cream);
    text-decoration: none;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    font-weight: 500;
    padding: 1rem 2.5rem;
    transition: background 0.2s, transform 0.1s;
    border: none;
    cursor: pointer;
  }
  .hero-cta:hover { background: var(--rust); }
  .hero-cta:active { transform: scale(0.98); }

  /* HORIZON LINE DIVIDER */
  .horizon {
    height: 6px;
    background: linear-gradient(90deg, var(--terra) 0%, var(--dust) 50%, var(--sky) 100%);
  }

  /* ABOUT */
  .section {
    padding: 5rem 2rem;
    max-width: 900px;
    margin: 0 auto;
  }
  .section-label {
    font-size: 0.65rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--terra);
    font-weight: 500;
    margin-bottom: 0.75rem;
  }
  .section h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 4vw, 2.8rem);
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 1.5rem;
    line-height: 1.2;
  }
  .section p {
    font-size: 1rem;
    color: #4a3c2e;
    line-height: 1.85;
    max-width: 640px;
    font-weight: 300;
    margin-bottom: 1rem;
  }

  /* SKILLS / WHAT I DO */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin-top: 3rem;
  }
  .skill-card {
    background: var(--sand);
    padding: 1.75rem;
    border-left: 3px solid var(--terra);
  }
  .skill-card .skill-num {
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    color: var(--terra);
    font-weight: 500;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
  }
  .skill-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: var(--ink);
    margin-bottom: 0.5rem;
  }
  .skill-card p {
    font-size: 0.85rem;
    color: #5a4a38;
    line-height: 1.7;
    margin: 0;
    font-weight: 400;
  }

  /* EXPERIENCE */
  .experience-section {
    background: var(--ink);
    padding: 5rem 2rem;
  }
  .experience-inner {
    max-width: 900px;
    margin: 0 auto;
  }
  .experience-inner .section-label { color: var(--terra); }
  .experience-inner h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 4vw, 2.8rem);
    color: var(--sand);
    margin-bottom: 3rem;
    line-height: 1.2;
  }
  .job {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 2rem;
    padding: 2rem 0;
    border-top: 1px solid #3a2c1e;
  }
  .job:last-child { border-bottom: 1px solid #3a2c1e; }
  .job-meta .year {
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--terra);
    font-weight: 500;
    margin-bottom: 0.4rem;
  }
  .job-meta .company {
    font-size: 0.9rem;
    color: var(--dust);
    font-weight: 400;
    line-height: 1.5;
  }
  .job-detail h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    color: var(--sand);
    margin-bottom: 0.5rem;
  }
  .job-detail p {
    font-size: 0.875rem;
    color: #a89880;
    line-height: 1.75;
    font-weight: 300;
  }

  /* CONTACT / FOOTER */
  .contact-section {
    background: var(--sand);
    padding: 6rem 2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .contact-section::before {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0; right: 0;
    height: 3px;
    background: var(--terra);
  }
  .contact-section .section-label { justify-content: center; display: block; }
  .contact-section h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 5vw, 3.5rem);
    color: var(--ink);
    margin: 0.5rem 0 1.5rem;
  }
  .contact-section p {
    color: #5a4a38;
    font-size: 1rem;
    font-weight: 300;
    max-width: 420px;
    margin: 0 auto 2.5rem;
    line-height: 1.8;
  }
  .linkedin-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    background: var(--ink);
    color: var(--sand);
    text-decoration: none;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    font-weight: 500;
    padding: 1rem 2.5rem;
    transition: background 0.2s;
  }
  .linkedin-btn:hover { background: var(--terra); }
  .linkedin-btn svg { width: 16px; height: 16px; flex-shrink: 0; }

  footer {
    background: var(--ink);
    padding: 1.5rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  footer span {
    font-size: 0.7rem;
    color: #6a5848;
    letter-spacing: 0.08em;
  }
  footer .footer-mark {
    font-family: 'Playfair Display', serif;
    font-size: 0.9rem;
    color: var(--dust);
  }

  @media (max-width: 600px) {
    .job { grid-template-columns: 1fr; gap: 0.5rem; }
    nav .nav-links { display: none; }
  }
</style>
</head>
<body>

<nav>
  <span class="logo">Chad Lock</span>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#work">Work</a>
    <a href="#experience">Experience</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<section class="hero">
  <div class="hero-texture"></div>
  <div class="hero-content">
    <p class="eyebrow">Brand &amp; Marketing — Denton, TX</p>
    <h1>
      Chad Lock.
      <span class="accent">Brand guy.</span>
    </h1>
    <p class="hero-tagline">
      I make credit unions look like they want to be there.
      Marketing, brand strategy, and digital stuff — with a design eye and a low tolerance for fluff.
    </p>
    <a href="#contact" class="hero-cta">Say hello</a>
  </div>
</section>

<div class="horizon"></div>

<section class="section" id="about">
  <p class="section-label">About</p>
  <h2>Marketing with a point of view.</h2>
  <p>
    I'm a Brand Coordinator at DATCU Credit Union, where I handle everything from billboard copy to website redesigns — and a few things in between that don't have a job title yet. My background is in design, but I've migrated toward strategy and digital over the years.
  </p>
  <p>
    Right now I'm deep in a HubSpot migration, wrangling 14 branch locations' worth of signage, and building AI integration into how our marketing team actually operates. It's a lot. It's also pretty fun.
  </p>
</section>

<section class="section" id="work" style="padding-top:0;">
  <p class="section-label">What I do</p>
  <h2>A few things, done well.</h2>
  <div class="skills-grid">
    <div class="skill-card">
      <div class="skill-num">01</div>
      <h3>Brand</h3>
      <p>Identity, voice, visual systems. Making sure everything looks intentional even when it wasn't.</p>
    </div>
    <div class="skill-card">
      <div class="skill-num">02</div>
      <h3>Digital Marketing</h3>
      <p>HubSpot, email, web strategy. Turning data into things that actually reach people.</p>
    </div>
    <div class="skill-card">
      <div class="skill-num">03</div>
      <h3>Design</h3>
      <p>Print, digital, environmental. I can make a brochure and a billboard and they'll look related.</p>
    </div>
    <div class="skill-card">
      <div class="skill-num">04</div>
      <h3>AI Integration</h3>
      <p>Finding practical ways to bring AI tools into a real marketing workflow. Still figuring it out. That's the point.</p>
    </div>
  </div>
</section>

<section class="experience-section" id="experience">
  <div class="experience-inner">
    <p class="section-label">Experience</p>
    <h2>Where I've been.</h2>

    <div class="job">
      <div class="job-meta">
        <div class="year">2019 — Present</div>
        <div class="company">DATCU Credit Union<br>Denton, TX</div>
      </div>
      <div class="job-detail">
        <h4>Brand Coordinator</h4>
        <p>Leading brand and marketing across a 14-branch credit union. Website redesign, HubSpot migration, branch graphics, billboards, social, email — plus building out an AI integration strategy for the marketing team.</p>
      </div>
    </div>

    <div class="job">
      <div class="job-meta">
        <div class="year">Earlier</div>
        <div class="company">Marketing &amp; Design<br>Various</div>
      </div>
      <div class="job-detail">
        <h4>Marketing &amp; Design Background</h4>
        <p>Years of brand, design, and marketing work across different roles and industries. Grew from production into strategy. Still design everything myself when I can.</p>
      </div>
    </div>

  </div>
</section>

<section class="contact-section" id="contact">
  <p class="section-label">Contact</p>
  <h2>Let's talk.</h2>
  <p>The best version of this conversation probably happens on LinkedIn. Find me there.</p>
  <a href="https://www.linkedin.com/in/chadlock" target="_blank" class="linkedin-btn">
    <svg viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
      <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
    </svg>
    View LinkedIn
  </a>
</section>

<footer>
  <span>chadlock.com</span>
  <span class="footer-mark">CL</span>
  <span>Denton, TX</span>
</footer>

</body>
</html>
