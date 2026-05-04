<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Justiniane Sandara | Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&family=Cormorant+Garamond:ital,wght@0,300;1,300;1,600&display=swap" rel="stylesheet">
<style>
  :root {
    --pink-deep: #c2185b;
    --pink-vivid: #e91e8c;
    --pink-mid: #f06292;
    --pink-soft: #f8bbd0;
    --pink-blush: #fce4ec;
    --pink-pale: #fff0f5;
    --cream: #fffaf9;
    --dark: #1a0a10;
    --mid: #5a2a3a;
    --light-text: #8d4060;
  }

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--dark);
    cursor: none;
    overflow-x: hidden;
  }

  /* Custom Cursor */
  .cursor {
    position: fixed;
    width: 12px; height: 12px;
    background: var(--pink-vivid);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s ease, background 0.2s;
    mix-blend-mode: multiply;
  }
  .cursor-ring {
    position: fixed;
    width: 36px; height: 36px;
    border: 1.5px solid var(--pink-mid);
    border-radius: 50%;
    pointer-events: none;
    z-index: 9998;
    transform: translate(-50%, -50%);
    transition: transform 0.18s ease, width 0.2s, height 0.2s;
  }

  /* Nav */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 22px 60px;
    background: rgba(255, 240, 245, 0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(240, 98, 146, 0.15);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--pink-deep);
    letter-spacing: 0.03em;
    text-decoration: none;
  }
  .nav-links { display: flex; gap: 38px; list-style: none; }
  .nav-links a {
    font-size: 0.82rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--mid);
    text-decoration: none;
    position: relative;
    transition: color 0.2s;
  }
  .nav-links a::after {
    content: '';
    position: absolute; bottom: -3px; left: 0;
    width: 0; height: 1.5px;
    background: var(--pink-vivid);
    transition: width 0.3s ease;
  }
  .nav-links a:hover { color: var(--pink-deep); }
  .nav-links a:hover::after { width: 100%; }

  /* ─── SECTION 1: HOME ─── */
  #home {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }
  .home-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 140px 70px 80px 90px;
    position: relative; z-index: 2;
  }
  .home-eyebrow {
    font-size: 0.75rem; letter-spacing: 0.25em; text-transform: uppercase;
    color: var(--pink-mid); font-weight: 500; margin-bottom: 20px;
    display: flex; align-items: center; gap: 12px;
  }
  .home-eyebrow::before {
    content: ''; width: 32px; height: 1px; background: var(--pink-mid);
  }
  .home-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 5vw, 5.5rem);
    font-weight: 900;
    line-height: 1.0;
    color: var(--dark);
    margin-bottom: 10px;
  }
  .home-name span {
    display: block;
    color: var(--pink-vivid);
    font-style: italic;
  }
  .home-tagline {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.35rem;
    font-style: italic;
    color: var(--light-text);
    margin: 22px 0 38px;
    line-height: 1.6;
  }
  .home-cta {
    display: inline-flex; align-items: center; gap: 12px;
    padding: 16px 36px;
    background: var(--pink-vivid);
    color: white;
    font-size: 0.82rem; letter-spacing: 0.15em; text-transform: uppercase;
    font-weight: 500;
    text-decoration: none;
    border-radius: 2px;
    width: fit-content;
    transition: background 0.25s, transform 0.2s;
    box-shadow: 0 8px 24px rgba(233, 30, 140, 0.35);
  }
  .home-cta:hover { background: var(--pink-deep); transform: translateY(-2px); }
  .home-cta::after { content: '→'; }

  .home-right {
    position: relative; overflow: hidden;
    background: linear-gradient(145deg, var(--pink-soft) 0%, var(--pink-blush) 60%, #ffd6e5 100%);
    display: flex; align-items: center; justify-content: center;
  }
  .home-blob {
    position: absolute; border-radius: 60% 40% 50% 60% / 50% 60% 40% 50%;
    animation: blobmorph 8s ease-in-out infinite alternate;
  }
  .blob1 {
    width: 420px; height: 420px;
    background: rgba(233,30,140,0.12);
    top: 15%; left: 10%;
  }
  .blob2 {
    width: 280px; height: 280px;
    background: rgba(194,24,91,0.1);
    bottom: 10%; right: 5%;
    animation-delay: -3s;
    border-radius: 40% 60% 60% 40% / 60% 40% 50% 50%;
  }
  @keyframes blobmorph {
    from { border-radius: 60% 40% 50% 60% / 50% 60% 40% 50%; }
    to   { border-radius: 40% 60% 60% 40% / 60% 40% 50% 60%; }
  }
  .home-photo-frame {
    position: relative; z-index: 2;
    width: 320px; height: 400px;
    border: 2px solid rgba(233,30,140,0.3);
    border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
    box-shadow: 20px 20px 60px rgba(194,24,91,0.15), -8px -8px 30px rgba(255,255,255,0.6);
  }
  .home-photo-initials {
    font-family: 'Playfair Display', serif;
    font-size: 6rem; font-weight: 900;
    color: var(--pink-vivid);
    opacity: 0.25;
    user-select: none;
  }
  .home-photo-label {
    position: absolute; bottom: 20px; left: 20px;
    font-family: 'Cormorant Garamond', serif;
    font-style: italic; font-size: 0.95rem;
    color: var(--mid);
  }
  .scroll-indicator {
    position: absolute; bottom: 36px; left: 50%;
    transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 8px;
    font-size: 0.72rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--pink-mid); z-index: 5;
  }
  .scroll-line {
    width: 1px; height: 50px;
    background: linear-gradient(to bottom, var(--pink-mid), transparent);
    animation: scrollDown 2s ease-in-out infinite;
  }
  @keyframes scrollDown {
    0%,100% { transform: scaleY(1); opacity: 1; }
    50% { transform: scaleY(0.5); opacity: 0.4; }
  }
  /* decorative petals */
  .petal {
    position: absolute;
    width: 18px; height: 26px;
    background: rgba(248,187,208,0.6);
    border-radius: 50% 50% 50% 0;
    animation: floatPetal linear infinite;
    pointer-events: none;
  }
  @keyframes floatPetal {
    0%   { transform: translateY(100vh) rotate(0deg); opacity:0; }
    10%  { opacity: 0.8; }
    90%  { opacity: 0.8; }
    100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
  }

  /* ─── SECTION 2: ABOUT ─── */
  #about {
    padding: 120px 90px;
    background: white;
    position: relative; overflow: hidden;
  }
  #about::before {
    content: 'ABOUT';
    position: absolute; right: -30px; top: 50%;
    transform: translateY(-50%) rotate(90deg);
    font-family: 'Playfair Display', serif;
    font-size: 8rem; font-weight: 900;
    color: var(--pink-blush);
    pointer-events: none; user-select: none;
    letter-spacing: 0.05em;
  }
  .section-header {
    margin-bottom: 70px;
  }
  .section-tag {
    font-size: 0.72rem; letter-spacing: 0.3em; text-transform: uppercase;
    color: var(--pink-mid); font-weight: 500; margin-bottom: 12px;
    display: flex; align-items: center; gap: 12px;
  }
  .section-tag::before { content: '✦'; font-size: 0.6rem; }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 3.5vw, 3.5rem);
    font-weight: 700; color: var(--dark);
    line-height: 1.15;
  }
  .section-title em { color: var(--pink-vivid); font-style: italic; }

  .about-grid {
    display: grid; grid-template-columns: 1fr 1.4fr; gap: 80px;
    align-items: center;
  }
  .about-visual {
    position: relative;
  }
  .about-card {
    background: linear-gradient(135deg, var(--pink-blush), var(--pink-soft));
    border-radius: 6px;
    padding: 50px 40px;
    text-align: center;
    position: relative;
    box-shadow: 0 20px 60px rgba(233,30,140,0.12);
  }
  .about-card::before {
    content: '';
    position: absolute; top: 12px; left: 12px; right: -12px; bottom: -12px;
    border: 2px solid var(--pink-soft);
    border-radius: 6px;
    z-index: -1;
  }
  .about-initial-big {
    font-family: 'Playfair Display', serif;
    font-size: 7rem; font-weight: 900;
    color: var(--pink-vivid); opacity: 0.2;
    line-height: 1;
  }
  .about-card-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem; font-weight: 700;
    color: var(--dark); margin-top: 10px;
  }
  .about-card-sub {
    font-size: 0.82rem; color: var(--pink-mid);
    letter-spacing: 0.1em; margin-top: 6px;
  }
  .about-badge {
    display: inline-block;
    margin-top: 20px;
    padding: 8px 20px;
    background: var(--pink-vivid);
    color: white;
    font-size: 0.78rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    border-radius: 2px;
  }
  .about-text h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem; font-weight: 700;
    color: var(--dark); margin-bottom: 20px;
  }
  .about-text p {
    font-size: 1rem; line-height: 1.85;
    color: var(--mid); margin-bottom: 18px;
  }
  .about-detail-row {
    display: flex; gap: 30px; margin-top: 34px; flex-wrap: wrap;
  }
  .about-detail {
    background: var(--pink-pale);
    border-left: 3px solid var(--pink-vivid);
    padding: 14px 20px; border-radius: 0 4px 4px 0;
    flex: 1; min-width: 200px;
  }
  .about-detail-label {
    font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--pink-mid); margin-bottom: 4px;
  }
  .about-detail-value {
    font-size: 0.92rem; font-weight: 500; color: var(--dark);
  }

  /* ─── SECTION 3: SKILLS ─── */
  #skills {
    padding: 120px 90px;
    background: linear-gradient(160deg, var(--dark) 0%, #3a0d22 50%, #1a0a10 100%);
    position: relative; overflow: hidden;
  }
  #skills .section-tag { color: var(--pink-mid); }
  #skills .section-title { color: white; }
  #skills::after {
    content: '';
    position: absolute; inset: 0;
    background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23c2185b' fill-opacity='0.04'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    pointer-events: none;
  }
  .skills-intro {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem; font-style: italic;
    color: rgba(248,187,208,0.7);
    max-width: 500px;
    margin-top: 14px; margin-bottom: 60px;
    line-height: 1.7;
  }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 20px;
  }
  .skill-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(248,187,208,0.12);
    border-radius: 8px;
    padding: 32px 28px;
    position: relative; overflow: hidden;
    transition: transform 0.25s, border-color 0.25s, background 0.25s;
    cursor: default;
  }
  .skill-card:hover {
    transform: translateY(-4px);
    border-color: rgba(233,30,140,0.4);
    background: rgba(233,30,140,0.06);
  }
  .skill-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--pink-vivid), var(--pink-mid));
    transform: scaleX(0); transform-origin: left;
    transition: transform 0.3s ease;
  }
  .skill-card:hover::before { transform: scaleX(1); }
  .skill-icon {
    font-size: 1.8rem; margin-bottom: 14px;
  }
  .skill-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.05rem; font-weight: 700;
    color: white; margin-bottom: 8px;
  }
  .skill-desc {
    font-size: 0.84rem; line-height: 1.65;
    color: rgba(248,187,208,0.55);
  }
  .skill-bar-wrap {
    margin-top: 16px;
    background: rgba(255,255,255,0.07);
    border-radius: 2px; height: 3px; overflow: hidden;
  }
  .skill-bar {
    height: 100%;
    background: linear-gradient(90deg, var(--pink-vivid), var(--pink-mid));
    border-radius: 2px;
    transform: scaleX(0); transform-origin: left;
    transition: transform 1.2s cubic-bezier(0.22, 1, 0.36, 1);
  }
  .skill-bar.animated { transform: scaleX(1); }

  /* ─── SECTION 4: INTERESTS ─── */
  #interests {
    padding: 120px 90px;
    background: var(--pink-pale);
    position: relative; overflow: hidden;
  }
  #interests::before {
    content: '❀';
    position: absolute; right: 60px; top: 40px;
    font-size: 12rem; color: var(--pink-soft);
    pointer-events: none; user-select: none;
    line-height: 1;
  }
  .interests-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 32px; margin-top: 60px;
  }
  .interest-card {
    background: white;
    border-radius: 12px;
    padding: 50px 36px 42px;
    text-align: center;
    box-shadow: 0 8px 40px rgba(233,30,140,0.08);
    border-bottom: 4px solid var(--pink-soft);
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
    position: relative; overflow: hidden;
  }
  .interest-card::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(160deg, var(--pink-blush) 0%, transparent 60%);
    opacity: 0; transition: opacity 0.3s;
  }
  .interest-card:hover {
    transform: translateY(-8px);
    border-color: var(--pink-vivid);
    box-shadow: 0 20px 60px rgba(233,30,140,0.18);
  }
  .interest-card:hover::before { opacity: 1; }
  .interest-emoji {
    font-size: 3rem; margin-bottom: 22px;
    display: block; position: relative; z-index: 1;
  }
  .interest-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 700;
    color: var(--dark); margin-bottom: 12px;
    position: relative; z-index: 1;
  }
  .interest-desc {
    font-size: 0.9rem; line-height: 1.7;
    color: var(--light-text);
    position: relative; z-index: 1;
  }
  .interest-tag {
    display: inline-block; margin-top: 18px;
    padding: 6px 16px;
    background: var(--pink-blush);
    color: var(--pink-deep);
    font-size: 0.75rem; letter-spacing: 0.12em; text-transform: uppercase;
    border-radius: 100px;
    position: relative; z-index: 1;
    transition: background 0.2s, color 0.2s;
  }
  .interest-card:hover .interest-tag {
    background: var(--pink-vivid); color: white;
  }

  /* ─── SECTION 5: CONTACT ─── */
  #contact {
    padding: 120px 90px;
    background: white;
    position: relative; overflow: hidden;
  }
  .contact-layout {
    display: grid; grid-template-columns: 1fr 1fr; gap: 80px;
    align-items: start; margin-top: 60px;
  }
  .contact-headline {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 2.5vw, 2.8rem);
    font-weight: 700; color: var(--dark);
    line-height: 1.3; margin-bottom: 20px;
  }
  .contact-headline em { color: var(--pink-vivid); font-style: italic; }
  .contact-subtext {
    font-size: 1rem; color: var(--mid); line-height: 1.8;
    margin-bottom: 40px;
  }
  .contact-items { display: flex; flex-direction: column; gap: 20px; }
  .contact-item {
    display: flex; align-items: flex-start; gap: 18px;
    padding: 22px 24px;
    border: 1px solid var(--pink-soft);
    border-radius: 8px;
    transition: border-color 0.25s, box-shadow 0.25s, transform 0.25s;
    text-decoration: none;
  }
  .contact-item:hover {
    border-color: var(--pink-mid);
    box-shadow: 0 6px 24px rgba(233,30,140,0.1);
    transform: translateX(4px);
  }
  .contact-item-icon {
    width: 46px; height: 46px; flex-shrink: 0;
    background: var(--pink-blush);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.3rem;
    transition: background 0.2s;
  }
  .contact-item:hover .contact-item-icon { background: var(--pink-vivid); }
  .contact-item-body {}
  .contact-item-label {
    font-size: 0.7rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--pink-mid); margin-bottom: 4px; font-weight: 500;
  }
  .contact-item-value {
    font-size: 0.98rem; font-weight: 500; color: var(--dark);
  }

  .contact-deco {
    position: relative; display: flex; align-items: center; justify-content: center;
  }
  .contact-big-circle {
    width: 380px; height: 380px;
    border-radius: 50%;
    background: linear-gradient(145deg, var(--pink-blush), var(--pink-soft));
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    gap: 16px;
    box-shadow: 0 30px 80px rgba(233,30,140,0.15), inset 0 0 0 2px rgba(233,30,140,0.12);
    text-align: center; padding: 40px;
  }
  .contact-big-letter {
    font-family: 'Playfair Display', serif;
    font-size: 5rem; font-weight: 900; line-height: 1;
    color: var(--pink-vivid);
  }
  .contact-big-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem; font-weight: 700; color: var(--dark);
    letter-spacing: 0.04em;
  }
  .contact-big-role {
    font-size: 0.82rem; color: var(--light-text); letter-spacing: 0.1em;
    text-transform: uppercase;
  }
  .contact-dots {
    position: absolute;
    width: 100%; height: 100%;
    top: 0; left: 0; pointer-events: none;
  }
  .contact-dot {
    position: absolute; width: 8px; height: 8px;
    border-radius: 50%; background: var(--pink-vivid); opacity: 0.25;
    animation: dotPulse 3s ease-in-out infinite;
  }
  @keyframes dotPulse {
    0%,100% { transform: scale(1); opacity: 0.25; }
    50% { transform: scale(1.8); opacity: 0.5; }
  }

  /* Footer */
  footer {
    padding: 30px 90px;
    background: var(--dark);
    display: flex; justify-content: space-between; align-items: center;
    flex-wrap: wrap; gap: 12px;
  }
  footer p {
    font-size: 0.8rem; color: rgba(248,187,208,0.4);
    letter-spacing: 0.1em;
  }
  .footer-sig {
    font-family: 'Playfair Display', serif;
    font-style: italic; color: var(--pink-mid); font-size: 1rem;
  }

  /* Animations */
  .fade-up {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .fade-up.visible { opacity: 1; transform: translateY(0); }
  .fade-up-delay-1 { transition-delay: 0.1s; }
  .fade-up-delay-2 { transition-delay: 0.2s; }
  .fade-up-delay-3 { transition-delay: 0.3s; }
  .fade-up-delay-4 { transition-delay: 0.4s; }
  .fade-up-delay-5 { transition-delay: 0.5s; }

  @media (max-width: 900px) {
    nav { padding: 18px 28px; }
    .nav-links { gap: 20px; }
    #home { grid-template-columns: 1fr; min-height: auto; }
    .home-left { padding: 120px 30px 60px; }
    .home-right { height: 320px; }
    #about, #skills, #interests, #contact { padding: 80px 30px; }
    .about-grid, .contact-layout { grid-template-columns: 1fr; gap: 40px; }
    .interests-grid { grid-template-columns: 1fr; }
    .contact-big-circle { width: 280px; height: 280px; }
    footer { padding: 24px 28px; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- Floating petals -->
<div class="petal" style="left:10%; animation-duration:9s; animation-delay:0s;"></div>
<div class="petal" style="left:25%; animation-duration:11s; animation-delay:-2s; width:12px; height:18px;"></div>
<div class="petal" style="left:55%; animation-duration:8s; animation-delay:-5s;"></div>
<div class="petal" style="left:75%; animation-duration:13s; animation-delay:-3s; width:14px; height:20px;"></div>
<div class="petal" style="left:88%; animation-duration:10s; animation-delay:-7s;"></div>

<!-- ── NAV ── -->
<nav>
  <a class="nav-logo" href="#home">JS</a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#interests">Interests</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- ── SECTION 1: HOME ── -->
<section id="home">
  <div class="home-left">
    <p class="home-eyebrow">Welcome to my portfolio</p>
    <h1 class="home-name fade-up">
      Justiniane,
      <span>Sandara</span>
    </h1>
    <p class="home-tagline fade-up fade-up-delay-1">
      Creative & passionate IT student<br>weaving art into technology.
    </p>
    <a href="#about" class="home-cta fade-up fade-up-delay-2">Discover More</a>
  </div>
  <div class="home-right">
    <div class="blob1 home-blob"></div>
    <div class="blob2 home-blob"></div>
    <div class="home-photo-frame">
      <div class="home-photo-initials">JS</div>
      <p class="home-photo-label">Justiniane Sandara</p>
    </div>
  </div>
  <div class="scroll-indicator">
    <div class="scroll-line"></div>
    scroll
  </div>
</section>

<!-- ── SECTION 2: ABOUT ── -->
<section id="about">
  <div class="section-header fade-up">
    <p class="section-tag">Section 02</p>
    <h2 class="section-title">About <em>Me</em></h2>
  </div>
  <div class="about-grid">
    <div class="about-visual fade-up">
      <div class="about-card">
        <div class="about-initial-big">JS</div>
        <p class="about-card-name">Justiniane Sandara</p>
        <p class="about-card-sub">12 — ITEM — 01</p>
        <div class="about-badge">IT Student</div>
      </div>
    </div>
    <div class="about-text fade-up fade-up-delay-1">
      <h3>Hello, I'm Sandara!</h3>
      <p>
        I am a dedicated student pursuing a <strong>Bachelor of Science in Information Technology</strong>, with a Major in <strong>Multimedia Arts and Animation</strong>.
      </p>
      <p>
        My academic journey blends the technical rigor of information technology with the creative world of multimedia arts — allowing me to explore design, animation, and digital storytelling alongside core IT principles.
      </p>
      <p>
        I believe creativity and technology go hand-in-hand, and I strive to bring both together in everything I do.
      </p>
      <div class="about-detail-row">
        <div class="about-detail">
          <p class="about-detail-label">Section</p>
          <p class="about-detail-value">12-ITEM-01</p>
        </div>
        <div class="about-detail">
          <p class="about-detail-label">Degree</p>
          <p class="about-detail-value">BSIT — Multimedia Arts & Animation</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── SECTION 3: SKILLS ── -->
<section id="skills">
  <div class="section-header fade-up">
    <p class="section-tag">Section 03</p>
    <h2 class="section-title">My <em style="color:var(--pink-mid)">Skills</em></h2>
  </div>
  <p class="skills-intro fade-up fade-up-delay-1">
    A blend of creative and technical capabilities shaped through study and passion.
  </p>
  <div class="skills-grid">
    <div class="skill-card fade-up fade-up-delay-1">
      <div class="skill-icon">🎨</div>
      <p class="skill-name">Multimedia Arts</p>
      <p class="skill-desc">Creating visual content, digital illustrations, and artistic compositions with an eye for detail and aesthetics.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.88"></div></div>
    </div>
    <div class="skill-card fade-up fade-up-delay-2">
      <div class="skill-icon">🎬</div>
      <p class="skill-name">Animation</p>
      <p class="skill-desc">Bringing characters and scenes to life through motion design principles and animation techniques.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.82"></div></div>
    </div>
    <div class="skill-card fade-up fade-up-delay-3">
      <div class="skill-icon">💻</div>
      <p class="skill-name">Information Technology</p>
      <p class="skill-desc">Foundation in IT concepts, systems, and problem-solving through a tech-driven academic program.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.80"></div></div>
    </div>
    <div class="skill-card fade-up fade-up-delay-1">
      <div class="skill-icon">🖥️</div>
      <p class="skill-name">Digital Design</p>
      <p class="skill-desc">Designing layouts, graphics, and visual media using digital tools and creative software.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.85"></div></div>
    </div>
    <div class="skill-card fade-up fade-up-delay-2">
      <div class="skill-icon">✍️</div>
      <p class="skill-name">Creative Arts</p>
      <p class="skill-desc">Expressing ideas through handcrafts, visual art, and imaginative creative work both digitally and physically.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.90"></div></div>
    </div>
    <div class="skill-card fade-up fade-up-delay-3">
      <div class="skill-icon">🤝</div>
      <p class="skill-name">Collaboration</p>
      <p class="skill-desc">Working effectively in teams, communicating clearly, and contributing positively to group projects and activities.</p>
      <div class="skill-bar-wrap"><div class="skill-bar" style="--w:0.87"></div></div>
    </div>
  </div>
</section>

<!-- ── SECTION 4: INTERESTS ── -->
<section id="interests">
  <div class="section-header fade-up">
    <p class="section-tag">Section 04</p>
    <h2 class="section-title">My <em>Interests</em></h2>
  </div>
  <div class="interests-grid">
    <div class="interest-card fade-up fade-up-delay-1">
      <span class="interest-emoji">✂️</span>
      <p class="interest-title">Hand Crafting</p>
      <p class="interest-desc">I love expressing creativity through handmade crafts — from cutting, folding, and shaping materials into beautiful, one-of-a-kind pieces that reflect my artistic vision.</p>
      <span class="interest-tag">DIY & Crafts</span>
    </div>
    <div class="interest-card fade-up fade-up-delay-2">
      <span class="interest-emoji">💐</span>
      <p class="interest-title">Bouquet Making</p>
      <p class="interest-desc">Arranging flowers into elegant bouquets is one of my great joys. I find peace and beauty in choosing blooms, colors, and textures to create meaningful floral designs.</p>
      <span class="interest-tag">Floral Art</span>
    </div>
    <div class="interest-card fade-up fade-up-delay-3">
      <span class="interest-emoji">🏸</span>
      <p class="interest-title">Playing Badminton</p>
      <p class="interest-desc">Badminton keeps me energized and focused. I enjoy the fast-paced rallies and the teamwork it builds — it's my way of staying active and having fun with friends.</p>
      <span class="interest-tag">Sport & Fitness</span>
    </div>
  </div>
</section>

<!-- ── SECTION 5: CONTACT ── -->
<section id="contact">
  <div class="section-header fade-up">
    <p class="section-tag">Section 05</p>
    <h2 class="section-title">Get in <em>Touch</em></h2>
  </div>
  <div class="contact-layout">
    <div class="fade-up">
      <h3 class="contact-headline">Let's <em>Connect</em> &amp; Collaborate</h3>
      <p class="contact-subtext">Feel free to reach out through any of the channels below. I'd love to hear from you!</p>
      <div class="contact-items">
        <a class="contact-item" href="mailto:justinianesandara0@gmail.com">
          <div class="contact-item-icon">📧</div>
          <div class="contact-item-body">
            <p class="contact-item-label">Email</p>
            <p class="contact-item-value">justinianesandara0@gmail.com</p>
          </div>
        </a>
        <a class="contact-item" href="tel:+639458021919">
          <div class="contact-item-icon">📱</div>
          <div class="contact-item-body">
            <p class="contact-item-label">Contact Number</p>
            <p class="contact-item-value">09458021919</p>
          </div>
        </a>
        <a class="contact-item" href="https://facebook.com" target="_blank">
          <div class="contact-item-icon">📘</div>
          <div class="contact-item-body">
            <p class="contact-item-label">Facebook</p>
            <p class="contact-item-value">Sandara Justiniane</p>
          </div>
        </a>
      </div>
    </div>
    <div class="contact-deco fade-up fade-up-delay-2">
      <div class="contact-dots">
        <div class="contact-dot" style="top:10%;left:15%;animation-delay:0s;"></div>
        <div class="contact-dot" style="top:20%;right:10%;animation-delay:0.5s;"></div>
        <div class="contact-dot" style="bottom:15%;left:20%;animation-delay:1s;"></div>
        <div class="contact-dot" style="bottom:25%;right:18%;animation-delay:1.5s;"></div>
      </div>
      <div class="contact-big-circle">
        <div class="contact-big-letter">JS</div>
        <p class="contact-big-name">Justiniane Sandara</p>
        <p class="contact-big-role">BSIT · Multimedia Arts &amp; Animation</p>
      </div>
    </div>
  </div>
</section>

<!-- Footer -->
<footer>
  <p>© 2024 Justiniane Sandara. All rights reserved.</p>
  <p class="footer-sig">Sandara Justiniane ✦</p>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });
  function animCursor() {
    cursor.style.left = mx + 'px'; cursor.style.top = my + 'px';
    rx += (mx - rx) * 0.14; ry += (my - ry) * 0.14;
    ring.style.left = rx + 'px'; ring.style.top = ry + 'px';
    requestAnimationFrame(animCursor);
  }
  animCursor();
  document.querySelectorAll('a, button').forEach(el => {
    el.addEventListener('mouseenter', () => { ring.style.width = '54px'; ring.style.height = '54px'; });
    el.addEventListener('mouseleave', () => { ring.style.width = '36px'; ring.style.height = '36px'; });
  });

  // Scroll animations
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        // Animate skill bars
        e.target.querySelectorAll && e.target.querySelectorAll('.skill-bar').forEach(b => b.classList.add('animated'));
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Also trigger skill bars on section entry
  const skillsObs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.querySelectorAll('.skill-bar').forEach((b, i) => {
          setTimeout(() => b.classList.add('animated'), i * 120 + 300);
        });
      }
    });
  }, { threshold: 0.2 });
  const skillsSection = document.getElementById('skills');
  if (skillsSection) skillsObs.observe(skillsSection);
</script>
</body>
</html>
