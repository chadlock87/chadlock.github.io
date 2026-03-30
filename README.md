<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chad Lock — real.fun.wow.</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>

/* ── TOKENS ─────────────────────────────────────────────── */
:root {
–bone:       #f2ede4;
–parchment:  #e8dfd0;
–dust:       #c9b99a;
–rust:       #b5490e;
–mesa:       #7a3a1e;
–shadow:     #1e140a;
–sage:       #7aab72;
–sky:        #a8c4d4;
–ink:        #2a1f14;
–mid:        #6b5a47;

–serif: ‘Playfair Display’, Georgia, serif;
–sans:  ‘DM Sans’, sans-serif;
}

/* ── RESET ───────────────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
background: var(–bone);
color: var(–ink);
font-family: var(–sans);
font-weight: 300;
line-height: 1.7;
overflow-x: hidden;
cursor: default;
}

/* ── GRAIN OVERLAY ───────────────────────────────────────── */
body::before {
content: ‘’;
position: fixed;
inset: 0;
pointer-events: none;
z-index: 999;
opacity: 0.045;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 256 256’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘noise’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23noise)’/%3E%3C/svg%3E”);
background-size: 180px;
}

/* ── NAV ─────────────────────────────────────────────────── */
nav {
position: fixed;
top: 0; left: 0; right: 0;
z-index: 100;
padding: 20px 40px;
display: flex;
align-items: center;
justify-content: space-between;
mix-blend-mode: multiply;
}

.nav-logo {
font-family: var(–serif);
font-size: 18px;
font-weight: 900;
color: var(–ink);
letter-spacing: -0.3px;
text-decoration: none;
}

.nav-links {
display: flex;
gap: 32px;
list-style: none;
}

.nav-links a {
font-size: 13px;
font-weight: 500;
letter-spacing: 1.2px;
text-transform: uppercase;
color: var(–mid);
text-decoration: none;
transition: color 0.2s;
}

.nav-links a:hover { color: var(–rust); }

/* ── HERO ─────────────────────────────────────────────────── */
#hero {
min-height: 100vh;
display: grid;
grid-template-columns: 1fr 1fr;
align-items: center;
padding: 120px 80px 80px;
position: relative;
overflow: hidden;
}

/* Horizon line texture */
#hero::after {
content: ‘’;
position: absolute;
bottom: 0; left: 0; right: 0;
height: 3px;
background: repeating-linear-gradient(90deg, var(–dust) 0px, var(–dust) 6px, transparent 6px, transparent 14px);
opacity: 0.5;
}

/* Big decorative “CL” watermark */
.hero-watermark {
position: absolute;
right: -20px;
top: 50%;
transform: translateY(-50%);
font-family: var(–serif);
font-size: clamp(180px, 22vw, 320px);
font-weight: 900;
font-style: italic;
color: var(–parchment);
line-height: 1;
pointer-events: none;
user-select: none;
letter-spacing: -10px;
}

.hero-left {
position: relative;
z-index: 2;
}

.hero-tag {
display: inline-flex;
align-items: center;
gap: 8px;
font-size: 12px;
font-weight: 500;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–rust);
margin-bottom: 24px;
opacity: 0;
animation: fadeUp 0.7s 0.1s forwards;
}

.hero-tag::before {
content: ‘’;
display: block;
width: 28px;
height: 2px;
background: var(–rust);
}

h1 {
font-family: var(–serif);
font-size: clamp(52px, 6vw, 88px);
font-weight: 900;
line-height: 1.0;
letter-spacing: -1.5px;
color: var(–ink);
margin-bottom: 10px;
opacity: 0;
animation: fadeUp 0.7s 0.2s forwards;
}

.hero-sub {
font-family: var(–serif);
font-size: clamp(20px, 2.5vw, 30px);
font-weight: 700;
font-style: italic;
color: var(–rust);
margin-bottom: 28px;
opacity: 0;
animation: fadeUp 0.7s 0.35s forwards;
}

.hero-bio {
font-size: 16px;
font-weight: 300;
color: var(–mid);
max-width: 420px;
margin-bottom: 40px;
line-height: 1.8;
opacity: 0;
animation: fadeUp 0.7s 0.5s forwards;
}

.hero-bio strong {
color: var(–ink);
font-weight: 500;
}

.hero-ctas {
display: flex;
align-items: center;
gap: 20px;
flex-wrap: wrap;
opacity: 0;
animation: fadeUp 0.7s 0.65s forwards;
}

.btn-primary {
padding: 13px 30px;
background: var(–rust);
color: var(–bone);
font-family: var(–sans);
font-size: 13px;
font-weight: 500;
letter-spacing: 1px;
text-transform: uppercase;
text-decoration: none;
border: 2px solid var(–rust);
transition: background 0.2s, color 0.2s, transform 0.15s;
display: inline-block;
}

.btn-primary:hover {
background: var(–mesa);
border-color: var(–mesa);
transform: translateY(-2px);
}

.btn-ghost {
padding: 13px 30px;
background: transparent;
color: var(–ink);
font-family: var(–sans);
font-size: 13px;
font-weight: 500;
letter-spacing: 1px;
text-transform: uppercase;
text-decoration: none;
border: 2px solid var(–dust);
transition: border-color 0.2s, color 0.2s, transform 0.15s;
display: inline-block;
}

.btn-ghost:hover {
border-color: var(–ink);
color: var(–rust);
transform: translateY(-2px);
}

/* Hero right: stacked label cards */
.hero-right {
position: relative;
z-index: 2;
display: flex;
flex-direction: column;
gap: 12px;
padding-left: 60px;
opacity: 0;
animation: fadeUp 0.8s 0.75s forwards;
}

.stat-card {
background: var(–parchment);
border-left: 4px solid var(–dust);
padding: 18px 22px;
transition: border-color 0.2s, transform 0.2s;
}

.stat-card:hover {
border-color: var(–rust);
transform: translateX(6px);
}

.stat-card.accent {
background: var(–rust);
border-color: var(–mesa);
}

.stat-num {
font-family: var(–serif);
font-size: 32px;
font-weight: 900;
color: var(–ink);
line-height: 1;
}

.stat-card.accent .stat-num { color: var(–bone); }

.stat-label {
font-size: 12px;
font-weight: 500;
letter-spacing: 0.8px;
text-transform: uppercase;
color: var(–mid);
margin-top: 3px;
}

.stat-card.accent .stat-label { color: rgba(242,237,228,0.7); }

/* ── SECTION SHARED ──────────────────────────────────────── */
section {
padding: 100px 80px;
}

.section-eyebrow {
font-size: 11px;
font-weight: 500;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–rust);
margin-bottom: 14px;
display: flex;
align-items: center;
gap: 10px;
}

.section-eyebrow::after {
content: ‘’;
flex: 1;
max-width: 40px;
height: 1px;
background: var(–rust);
}

h2 {
font-family: var(–serif);
font-size: clamp(36px, 4vw, 58px);
font-weight: 900;
line-height: 1.05;
letter-spacing: -1px;
color: var(–ink);
margin-bottom: 20px;
}

h2 em {
font-style: italic;
color: var(–rust);
}

/* ── ABOUT ───────────────────────────────────────────────── */
#about {
background: var(–parchment);
display: grid;
grid-template-columns: 1fr 1fr;
gap: 80px;
align-items: start;
position: relative;
overflow: hidden;
}

#about::before {
content: ‘real.’;
position: absolute;
bottom: -20px;
right: -10px;
font-family: var(–serif);
font-size: 160px;
font-weight: 900;
font-style: italic;
color: var(–dust);
opacity: 0.25;
pointer-events: none;
line-height: 1;
}

.about-text p {
font-size: 16px;
color: var(–mid);
line-height: 1.9;
margin-bottom: 18px;
}

.about-text p strong {
color: var(–ink);
font-weight: 500;
}

.about-text p:first-of-type {
font-size: 19px;
font-weight: 400;
color: var(–ink);
}

.pill-row {
display: flex;
flex-wrap: wrap;
gap: 8px;
margin-top: 28px;
}

.pill {
padding: 6px 16px;
border: 1.5px solid var(–dust);
font-size: 12px;
font-weight: 500;
letter-spacing: 0.5px;
color: var(–mid);
background: transparent;
transition: border-color 0.2s, color 0.2s, background 0.2s;
}

.pill:hover {
border-color: var(–rust);
color: var(–rust);
background: rgba(181,73,14,0.05);
}

/* About right: values */
.about-values {
display: flex;
flex-direction: column;
gap: 0;
}

.value-item {
padding: 28px 0;
border-bottom: 1px solid var(–dust);
display: grid;
grid-template-columns: 48px 1fr;
gap: 16px;
align-items: start;
}

.value-item:last-child { border-bottom: none; }

.value-num {
font-family: var(–serif);
font-size: 13px;
font-style: italic;
color: var(–dust);
padding-top: 4px;
}

.value-title {
font-family: var(–serif);
font-size: 20px;
font-weight: 700;
color: var(–ink);
margin-bottom: 6px;
}

.value-desc {
font-size: 14px;
color: var(–mid);
line-height: 1.7;
}

/* ── WORK ────────────────────────────────────────────────── */
#work {
background: var(–bone);
}

.work-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 2px;
margin-top: 52px;
background: var(–dust);
}

.work-card {
background: var(–bone);
padding: 36px 30px;
position: relative;
overflow: hidden;
transition: background 0.25s;
cursor: default;
}

.work-card:hover { background: var(–parchment); }

.work-card::after {
content: attr(data-num);
position: absolute;
bottom: -16px;
right: 12px;
font-family: var(–serif);
font-size: 80px;
font-weight: 900;
font-style: italic;
color: var(–parchment);
line-height: 1;
pointer-events: none;
transition: color 0.25s;
}

.work-card:hover::after { color: var(–dust); }

.work-icon {
font-size: 28px;
margin-bottom: 16px;
display: block;
}

.work-title {
font-family: var(–serif);
font-size: 22px;
font-weight: 700;
color: var(–ink);
margin-bottom: 10px;
line-height: 1.2;
}

.work-desc {
font-size: 14px;
color: var(–mid);
line-height: 1.7;
}

.work-tag {
display: inline-block;
margin-top: 16px;
font-size: 11px;
font-weight: 500;
letter-spacing: 1.5px;
text-transform: uppercase;
color: var(–rust);
}

/* ── CALICHE ─────────────────────────────────────────────── */
#caliche {
background: var(–shadow);
color: var(–bone);
position: relative;
overflow: hidden;
}

#caliche::before {
content: ‘’;
position: absolute;
inset: 0;
background:
radial-gradient(ellipse 60% 50% at 80% 50%, rgba(181,73,14,0.15) 0%, transparent 70%),
repeating-linear-gradient(0deg, transparent, transparent 40px, rgba(255,255,255,0.015) 40px, rgba(255,255,255,0.015) 41px);
pointer-events: none;
}

.caliche-inner {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 80px;
align-items: center;
position: relative;
z-index: 1;
}

#caliche .section-eyebrow { color: var(–sage); }
#caliche .section-eyebrow::after { background: var(–sage); }

#caliche h2 { color: var(–bone); }
#caliche h2 em { color: var(–rust); }

#caliche p {
font-size: 16px;
color: rgba(242,237,228,0.65);
line-height: 1.9;
margin-bottom: 16px;
}

#caliche p strong { color: var(–bone); font-weight: 500; }

.caliche-right {
display: flex;
flex-direction: column;
gap: 14px;
}

.caliche-feature {
display: flex;
align-items: flex-start;
gap: 16px;
padding: 20px;
border: 1px solid rgba(255,255,255,0.08);
background: rgba(255,255,255,0.04);
transition: background 0.2s, border-color 0.2s;
}

.caliche-feature:hover {
background: rgba(181,73,14,0.12);
border-color: rgba(181,73,14,0.3);
}

.cf-icon {
font-size: 22px;
flex-shrink: 0;
margin-top: 2px;
}

.cf-title {
font-family: var(–serif);
font-size: 16px;
font-weight: 700;
color: var(–bone);
margin-bottom: 4px;
}

.cf-desc {
font-size: 13px;
color: rgba(242,237,228,0.55);
line-height: 1.6;
}

/* ── CONNECT ─────────────────────────────────────────────── */
#connect {
background: var(–bone);
text-align: center;
padding: 120px 80px;
position: relative;
overflow: hidden;
}

#connect::before {
content: ‘wow.’;
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
font-family: var(–serif);
font-size: clamp(100px, 18vw, 220px);
font-weight: 900;
font-style: italic;
color: var(–parchment);
pointer-events: none;
white-space: nowrap;
line-height: 1;
}

.connect-inner {
position: relative;
z-index: 1;
max-width: 560px;
margin: 0 auto;
}

#connect .section-eyebrow {
justify-content: center;
display: flex;
}

#connect .section-eyebrow::after { display: none; }
#connect .section-eyebrow::before {
content: ‘’;
max-width: 40px;
height: 1px;
background: var(–rust);
display: block;
}

#connect h2 { text-align: center; }

#connect p {
font-size: 17px;
color: var(–mid);
margin-bottom: 40px;
line-height: 1.8;
}

.connect-links {
display: flex;
justify-content: center;
flex-wrap: wrap;
gap: 14px;
}

.connect-link {
display: flex;
align-items: center;
gap: 8px;
padding: 12px 24px;
border: 1.5px solid var(–dust);
font-size: 13px;
font-weight: 500;
letter-spacing: 0.5px;
color: var(–ink);
text-decoration: none;
transition: border-color 0.2s, color 0.2s, transform 0.15s;
}

.connect-link:hover {
border-color: var(–rust);
color: var(–rust);
transform: translateY(-2px);
}

/* ── FOOTER ──────────────────────────────────────────────── */
footer {
background: var(–ink);
padding: 32px 80px;
display: flex;
align-items: center;
justify-content: space-between;
}

.footer-logo {
font-family: var(–serif);
font-size: 16px;
font-weight: 900;
font-style: italic;
color: var(–bone);
letter-spacing: -0.3px;
}

.footer-tagline {
font-size: 12px;
font-weight: 500;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–dust);
}

.footer-copy {
font-size: 12px;
color: var(–mid);
}

/* ── ANIMATIONS ──────────────────────────────────────────── */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(20px); }
to   { opacity: 1; transform: translateY(0); }
}

/* Scroll-triggered fade */
.reveal {
opacity: 0;
transform: translateY(28px);
transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
opacity: 1;
transform: translateY(0);
}

/* ── RESPONSIVE ──────────────────────────────────────────── */
@media (max-width: 900px) {
nav { padding: 18px 24px; }
.nav-links { display: none; }

#hero {
grid-template-columns: 1fr;
padding: 110px 24px 60px;
gap: 48px;
}
.hero-watermark { display: none; }
.hero-right { padding-left: 0; }

section { padding: 72px 24px; }

#about, .caliche-inner {
grid-template-columns: 1fr;
gap: 48px;
}

.work-grid { grid-template-columns: 1fr; }

footer {
flex-direction: column;
gap: 10px;
text-align: center;
padding: 28px 24px;
}

#connect { padding: 80px 24px; }
}
</style>

</head>
<body>

<!-- NAV -->

<nav>
  <a href="#" class="nav-logo">Chad Lock</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#work">Work</a></li>
    <li><a href="#connect">Connect</a></li>
  </ul>
</nav>

<!-- HERO -->

<section id="hero">
  <div class="hero-left">
    <div class="hero-tag">Corinth, TX &nbsp;·&nbsp; Brand + Digital</div>
    <h1>Chad<br>Lock.</h1>
    <div class="hero-sub">real. fun. wow.</div>
    <p class="hero-bio">
      Brand Coordinator. Creative strategist.
      I build things that connect — campaigns, communities, and the occasional killer idea.
    </p>
    <div class="hero-ctas">
      <a href="#work" class="btn-primary">See the Work</a>
      <a href="#connect" class="btn-ghost">Say Hello</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="stat-card accent">
      <div class="stat-num">14</div>
      <div class="stat-label">Branch locations branded</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">∞</div>
      <div class="stat-label">Ideas in the queue</div>
    </div>
  </div>
  <div class="hero-watermark" aria-hidden="true">CL</div>
</section>

<!-- ABOUT -->

<section id="about">
  <div class="about-text reveal">
    <div class="section-eyebrow">About</div>
    <h2>The<br><em>real</em> story.</h2>
    <p>
      I'm a brand and digital marketing coordinator at DATCU Credit Union — a community financial institution with 14 branches across North Texas.
      My work spans the full creative stack: <strong>brand identity, digital campaigns, HubSpot strategy, billboard copy, social, and now AI integration.</strong>
    </p>
    <p>
      I'm an Oklahoma State grad, a Formula 1 fan, and the kind of person who has opinions about typefaces at a dinner party.
      Wet Leg and Typhoon are on the rotation. My kids think I'm hilarious. The jury's still out.
    </p>
    <div class="pill-row">
      <span class="pill">Brand Strategy</span>
      <span class="pill">HubSpot</span>
      <span class="pill">Digital Marketing</span>
      <span class="pill">AI Integration</span>
      <span class="pill">Graphic Design</span>
      <span class="pill">Copywriting</span>
      <span class="pill">Campaign Development</span>
      <span class="pill">Print Production</span>
    </div>
  </div>
  <div class="about-values reveal">
    <div class="value-item">
      <span class="value-num">01</span>
      <div>
        <div class="value-title">real.</div>
        <div class="value-desc">No pretense. The best creative work is honest work. I'd rather say something true in plain language than say nothing beautifully.</div>
      </div>
    </div>
    <div class="value-item">
      <span class="value-num">02</span>
      <div>
        <div class="value-title">fun.</div>
        <div class="value-desc">I take the work seriously. Myself, considerably less so. Levity is a skill and I've been practicing.</div>
      </div>
    </div>
    <div class="value-item">
      <span class="value-num">03</span>
      <div>
        <div class="value-title">wow.</div>
        <div class="value-desc">The standard isn't good enough. If it doesn't make someone stop scrolling, stop walking, stop and actually look — we're not done yet.</div>
      </div>
    </div>
  </div>
</section>

<!-- WORK -->

<section id="work">
  <div class="reveal">
    <div class="section-eyebrow">Work</div>
    <h2>What I<br><em>actually</em> do.</h2>
  </div>
  <div class="work-grid">
    <div class="work-card reveal" data-num="1">
      <span class="work-icon">🏦</span>
      <div class="work-title">Brand & Campaign</div>
      <div class="work-desc">Full brand stewardship for a 14-branch credit union — from interior graphics and billboards to NIL athlete campaigns at UNT. If members see it, I touched it.</div>
      <span class="work-tag">DATCU Credit Union</span>
    </div>
    <div class="work-card reveal" data-num="2">
      <span class="work-icon">⚙️</span>
      <div class="work-title">Digital & HubSpot</div>
      <div class="work-desc">Leading a full website migration from Kentico to HubSpot. Evaluating calculator vendors, building automation workflows, and architecting how members actually experience the brand online.</div>
      <span class="work-tag">Web · CRM · Automation</span>
    </div>
    <div class="work-card reveal" data-num="3">
      <span class="work-icon">🤖</span>
      <div class="work-title">AI Integration</div>
      <div class="work-desc">Building an AI strategy across the marketing department — phased rollout covering social, email, billboards, and beyond. Bridging the gap between what's possible and what's practical.</div>
      <span class="work-tag">Strategy · Tooling</span>
    </div>
  </div>
</section>

<!-- CONNECT -->

<section id="connect">
  <div class="connect-inner">
    <div class="section-eyebrow">Connect</div>
    <h2>Let's make<br>something <em>good.</em></h2>
    <p>Whether it's a brand challenge, a creative collab, or you just want to talk about F1 strategy or West Texas music — the door's open.</p>
    <div class="connect-links">
      <a href="https://linkedin.com/in/chadlock" class="connect-link" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:chad@chadlock.com" class="connect-link">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,12 2,6"/></svg>
        Email Me
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <span class="footer-logo">Chad Lock</span>
  <span class="footer-tagline">real. fun. wow.</span>
  <span class="footer-copy">© 2025 · Corinth, TX</span>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Smooth range fill for slider
  const slider = document.getElementById ? null : null; // not used here
</script>

</body>
</html>
