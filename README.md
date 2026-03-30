# Abmanmedia
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abman Media — Grow Your Business Online</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --white: #f5f2ec;
    --gold: #c9a84c;
    --gold-light: #e8d5a0;
    --card-bg: #161616;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--black);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 9998; opacity: 0.4;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 200;
    display: flex; justify-content: space-between; align-items: center;
    padding: 24px 60px;
    background: rgba(10,10,10,0.96);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 22px; font-weight: 700; letter-spacing: 0.05em;
    color: var(--white); text-decoration: none; position: relative; z-index: 201;
  }
  .nav-logo span { color: var(--gold); }
  .nav-links { display: flex; gap: 40px; list-style: none; align-items: center; }
  .nav-links a {
    color: var(--white); text-decoration: none;
    font-size: 13px; letter-spacing: 0.12em; text-transform: uppercase;
    opacity: 0.7; transition: opacity 0.3s;
  }
  .nav-links a:hover { opacity: 1; }
  .nav-cta {
    background: var(--gold); color: var(--black) !important;
    padding: 10px 24px; opacity: 1 !important; font-weight: 500;
  }
  .nav-cta:hover { background: var(--gold-light) !important; }

  /* HAMBURGER */
  .hamburger {
    display: none; flex-direction: column; gap: 5px;
    cursor: pointer; padding: 4px; z-index: 201;
    background: none; border: none; position: relative;
  }
  .hamburger span {
    display: block; width: 24px; height: 2px;
    background: var(--white); border-radius: 2px;
    transition: transform 0.3s, opacity 0.3s;
  }
  .hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .hamburger.open span:nth-child(2) { opacity: 0; }
  .hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  /* MOBILE MENU */
  .mobile-menu {
    display: none; position: fixed; inset: 0;
    background: rgba(10,10,10,0.99); z-index: 199;
    flex-direction: column; align-items: center; justify-content: center;
    gap: 36px; opacity: 0; transition: opacity 0.3s;
  }
  .mobile-menu.open { opacity: 1; }
  .mobile-menu a {
    color: var(--white); text-decoration: none;
    font-family: 'Playfair Display', serif;
    font-size: 30px; font-weight: 700;
    opacity: 0.8; transition: color 0.3s, opacity 0.3s;
  }
  .mobile-menu a:hover { color: var(--gold); opacity: 1; }
  .mobile-cta {
    background: var(--gold); color: var(--black) !important;
    padding: 14px 40px; font-family: 'DM Sans', sans-serif !important;
    font-size: 13px !important; letter-spacing: 0.1em; text-transform: uppercase;
    opacity: 1 !important;
  }
  .mob-contacts {
    display: flex; flex-direction: column; align-items: center; gap: 10px;
    margin-top: 8px; padding-top: 24px;
    border-top: 1px solid rgba(255,255,255,0.08); width: 80%;
  }
  .mob-contacts a {
    font-family: 'DM Sans', sans-serif !important;
    font-size: 14px !important; color: rgba(245,242,236,0.45) !important;
    letter-spacing: 0.04em;
  }

  /* HERO */
  .hero {
    min-height: 100vh; display: flex; flex-direction: column;
    justify-content: center; padding: 130px 60px 80px;
    position: relative; overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 60% 70% at 80% 50%, rgba(201,168,76,0.08) 0%, transparent 70%),
      radial-gradient(ellipse 40% 50% at 10% 80%, rgba(201,168,76,0.05) 0%, transparent 60%);
  }
  .hero-line {
    position: absolute; top: 0; right: 160px;
    width: 1px; height: 100%;
    background: linear-gradient(to bottom, transparent, rgba(201,168,76,0.3), transparent);
  }
  .hero-content { position: relative; max-width: 780px; }
  .hero-tag {
    display: inline-flex; align-items: center; gap: 10px;
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 32px;
    opacity: 0; animation: fadeUp 0.8s 0.2s forwards;
  }
  .hero-tag::before {
    content: ''; display: block; width: 32px; height: 1px;
    background: var(--gold); flex-shrink: 0;
  }
  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 7vw, 90px);
    font-weight: 900; line-height: 1.0; letter-spacing: -0.02em;
    margin-bottom: 28px;
    opacity: 0; animation: fadeUp 0.8s 0.4s forwards;
  }
  h1 em { font-style: italic; color: var(--gold); }
  .hero-sub {
    font-size: 17px; line-height: 1.7;
    color: rgba(245,242,236,0.6); max-width: 520px; margin-bottom: 40px;
    opacity: 0; animation: fadeUp 0.8s 0.6s forwards;
  }
  .hero-actions {
    display: flex; gap: 20px; align-items: center; flex-wrap: wrap;
    opacity: 0; animation: fadeUp 0.8s 0.8s forwards;
  }

  /* Stats — desktop float */
  .hero-stats {
    position: absolute; right: 60px; bottom: 80px;
    display: flex; flex-direction: column; gap: 32px;
    opacity: 0; animation: fadeLeft 0.8s 1s forwards;
  }
  .hero-stats .stat {
    text-align: right;
    border-right: 1px solid rgba(201,168,76,0.3);
    padding-right: 24px;
  }
  /* Stats — mobile inline */
  .hero-stats-inline {
    display: none; gap: 0;
    margin-top: 48px; padding-top: 32px;
    border-top: 1px solid rgba(201,168,76,0.15);
    opacity: 0; animation: fadeUp 0.8s 1s forwards;
  }
  .hero-stats-inline .stat {
    flex: 1; text-align: center; padding: 0 12px;
    border-right: 1px solid rgba(201,168,76,0.2);
  }
  .hero-stats-inline .stat:last-child { border-right: none; }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 36px; font-weight: 700; color: var(--gold); line-height: 1;
  }
  .stat-label {
    font-size: 10px; letter-spacing: 0.15em; text-transform: uppercase;
    color: rgba(245,242,236,0.4); margin-top: 4px;
  }

  .btn-primary {
    background: var(--gold); color: var(--black);
    padding: 16px 36px; font-family: 'DM Sans', sans-serif;
    font-size: 14px; font-weight: 500; letter-spacing: 0.08em;
    text-transform: uppercase; text-decoration: none;
    border: none; cursor: pointer;
    transition: background 0.3s, transform 0.2s;
    display: inline-block; white-space: nowrap;
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }
  .btn-ghost {
    color: var(--white); text-decoration: none;
    font-size: 14px; letter-spacing: 0.08em; text-transform: uppercase;
    display: flex; align-items: center; gap: 8px;
    opacity: 0.6; transition: opacity 0.3s; white-space: nowrap;
  }
  .btn-ghost:hover { opacity: 1; }
  .btn-ghost::after { content: '→'; transition: transform 0.3s; }
  .btn-ghost:hover::after { transform: translateX(4px); }

  /* MARQUEE */
  .marquee-section {
    border-top: 1px solid rgba(255,255,255,0.06);
    border-bottom: 1px solid rgba(255,255,255,0.06);
    padding: 20px 0; overflow: hidden;
    background: rgba(201,168,76,0.04);
  }
  .marquee-track {
    display: flex; gap: 60px;
    animation: marquee 18s linear infinite; white-space: nowrap;
  }
  .marquee-item {
    font-size: 11px; letter-spacing: 0.25em; text-transform: uppercase;
    color: rgba(245,242,236,0.35); flex-shrink: 0;
    display: flex; align-items: center; gap: 60px;
  }
  .marquee-item::after { content: '✦'; color: var(--gold); opacity: 0.5; }

  /* SERVICES */
  .services { padding: 120px 60px; }
  .section-header {
    display: flex; justify-content: space-between;
    align-items: flex-end; margin-bottom: 80px;
  }
  .section-tag {
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--gold); margin-bottom: 16px;
  }
  h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(30px, 4vw, 54px); font-weight: 700; line-height: 1.1;
  }
  .section-desc {
    max-width: 340px; font-size: 15px; line-height: 1.7;
    color: rgba(245,242,236,0.5); text-align: right;
  }
  .services-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2px; }
  .service-card {
    background: var(--card-bg); padding: 48px 40px;
    position: relative; overflow: hidden; transition: background 0.4s;
  }
  .service-card::before {
    content: ''; position: absolute; bottom: 0; left: 0;
    width: 100%; height: 2px; background: var(--gold);
    transform: scaleX(0); transform-origin: left; transition: transform 0.4s;
  }
  .service-card:hover { background: #1c1c1c; }
  .service-card:hover::before { transform: scaleX(1); }
  .service-num {
    font-family: 'Playfair Display', serif; font-size: 60px;
    font-weight: 900; color: rgba(201,168,76,0.1); line-height: 1;
    margin-bottom: 24px; transition: color 0.4s;
  }
  .service-card:hover .service-num { color: rgba(201,168,76,0.2); }
  .service-icon { font-size: 28px; margin-bottom: 20px; }
  .service-title {
    font-family: 'Playfair Display', serif; font-size: 22px;
    font-weight: 700; margin-bottom: 16px;
  }
  .service-desc { font-size: 14px; line-height: 1.8; color: rgba(245,242,236,0.5); }
  .service-price {
    margin-top: 32px; font-size: 12px; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--gold);
  }

  /* PROCESS */
  .process { padding: 120px 60px; background: #0d0d0d; }
  .process-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: center; margin-top: 80px;
  }
  .process-steps { display: flex; flex-direction: column; }
  .process-step {
    display: flex; gap: 32px; padding: 32px 0;
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }
  .process-step:last-child { border-bottom: none; }
  .step-num {
    font-family: 'Playfair Display', serif; font-size: 13px;
    color: var(--gold); font-weight: 700; flex-shrink: 0; margin-top: 3px;
  }
  .step-content h3 {
    font-family: 'Playfair Display', serif; font-size: 20px; margin-bottom: 10px;
  }
  .step-content p { font-size: 14px; line-height: 1.7; color: rgba(245,242,236,0.5); }
  .process-visual {
    position: relative; height: 480px; background: var(--card-bg);
    display: flex; align-items: center; justify-content: center; overflow: hidden;
  }
  .process-visual::before {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(ellipse at center, rgba(201,168,76,0.12) 0%, transparent 70%);
  }
  .visual-phone {
    width: 200px; height: 360px;
    border: 2px solid rgba(201,168,76,0.3); border-radius: 28px;
    background: #0a0a0a; display: flex; flex-direction: column; overflow: hidden;
  }
  .phone-notch {
    width: 60px; height: 6px; background: rgba(201,168,76,0.3);
    border-radius: 3px; margin: 16px auto 0;
  }
  .phone-screen {
    flex: 1; padding: 16px; display: flex;
    flex-direction: column; gap: 8px; margin-top: 16px;
  }
  .phone-bar { height: 8px; background: rgba(201,168,76,0.2); border-radius: 4px; }
  .phone-bar.short { width: 60%; }
  .phone-bar.gold { background: rgba(201,168,76,0.5); height: 32px; border-radius: 6px; margin-top: 8px; }
  .phone-bar.img { height: 80px; background: rgba(201,168,76,0.08); border-radius: 6px; margin-top: 4px; }
  .visual-badge {
    position: absolute; top: 32px; right: 0;
    background: var(--gold); color: var(--black);
    padding: 10px 18px; font-size: 11px; font-weight: 500;
    letter-spacing: 0.1em; text-transform: uppercase;
  }
  .visual-badge2 {
    position: absolute; bottom: 32px; left: 0;
    background: var(--card-bg); border: 1px solid rgba(201,168,76,0.3);
    color: var(--white); padding: 14px 20px; font-size: 12px;
  }
  .badge2-num {
    font-family: 'Playfair Display', serif; font-size: 28px;
    color: var(--gold); font-weight: 700;
  }

  /* WHY */
  .why { padding: 120px 60px; }
  .why-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 2px; margin-top: 80px;
  }
  .why-card {
    background: var(--card-bg); padding: 40px 32px;
    border-top: 2px solid transparent; transition: border-color 0.4s;
  }
  .why-card:hover { border-top-color: var(--gold); }
  .why-icon {
    width: 48px; height: 48px; border: 1px solid rgba(201,168,76,0.3);
    display: flex; align-items: center; justify-content: center;
    font-size: 20px; margin-bottom: 24px;
  }
  .why-title { font-family: 'Playfair Display', serif; font-size: 18px; margin-bottom: 12px; }
  .why-desc { font-size: 13px; line-height: 1.8; color: rgba(245,242,236,0.45); }

  /* CTA */
  .cta-section {
    padding: 120px 60px; background: #0d0d0d;
    text-align: center; position: relative; overflow: hidden;
  }
  .cta-section::before {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at center, rgba(201,168,76,0.07) 0%, transparent 70%);
  }
  .cta-section h2 { font-size: clamp(34px, 5vw, 68px); margin-bottom: 24px; position: relative; }
  .cta-section p {
    font-size: 17px; color: rgba(245,242,236,0.5);
    margin-bottom: 48px; position: relative; line-height: 1.7;
  }
  .cta-actions {
    display: flex; gap: 20px; justify-content: center;
    align-items: center; position: relative; flex-wrap: wrap;
  }
  .contact-links {
    margin-top: 48px; display: flex; gap: 40px;
    justify-content: center; position: relative; flex-wrap: wrap;
  }
  .contact-link {
    display: flex; align-items: center; gap: 10px;
    font-size: 13px; color: rgba(245,242,236,0.5);
    text-decoration: none; letter-spacing: 0.05em; transition: color 0.3s;
  }
  .contact-link:hover { color: var(--gold); }
  .contact-link span {
    width: 32px; height: 32px; border: 1px solid rgba(255,255,255,0.1);
    border-radius: 50%; display: flex; align-items: center;
    justify-content: center; font-size: 14px;
  }

  /* FOOTER */
  footer {
    padding: 40px 60px; border-top: 1px solid rgba(255,255,255,0.06);
    display: flex; justify-content: space-between; align-items: center;
  }
  .footer-logo { font-family: 'Playfair Display', serif; font-size: 18px; font-weight: 700; }
  .footer-logo span { color: var(--gold); }
  .footer-copy { font-size: 12px; color: rgba(245,242,236,0.3); letter-spacing: 0.05em; }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeLeft {
    from { opacity: 0; transform: translateX(24px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }
  .reveal { opacity: 0; transform: translateY(32px); transition: opacity 0.8s, transform 0.8s; }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* MOBILE — iPhone Pro Max and all phones */
  @media (max-width: 768px) {
    nav { padding: 18px 24px; }
    .nav-links { display: none; }
    .hamburger { display: flex; }

    .hero { padding: 100px 24px 64px; }
    .hero-line { display: none; }
    .hero-stats { display: none; }
    .hero-stats-inline { display: flex; }
    .hero-stats-inline .stat-num { font-size: 30px; }
    .hero-sub { font-size: 16px; max-width: 100%; }
    .hero-actions { flex-direction: column; align-items: stretch; gap: 14px; }
    .btn-primary { text-align: center; padding: 18px 24px; }
    .btn-ghost { justify-content: center; }

    .services { padding: 72px 20px; }
    .section-header { flex-direction: column; gap: 16px; margin-bottom: 40px; }
    .section-desc { text-align: left; max-width: 100%; }
    .services-grid { grid-template-columns: 1fr; }
    .service-card { padding: 36px 24px; }
    .service-num { font-size: 44px; }

    .process { padding: 72px 20px; }
    .process-grid { grid-template-columns: 1fr; gap: 0; margin-top: 48px; }
    .process-visual {
      height: 220px; margin-top: 32px;
      border-radius: 8px;
    }
    .visual-phone { width: 110px; height: 190px; border-radius: 18px; }
    .phone-notch { width: 36px; height: 4px; margin: 10px auto 0; }
    .phone-bar { height: 5px; }
    .phone-bar.gold { height: 22px; }
    .phone-bar.img { height: 48px; }
    .visual-badge { font-size: 10px; padding: 8px 12px; top: 16px; right: 0; }
    .visual-badge2 { padding: 10px 14px; bottom: 16px; left: 0; }
    .badge2-num { font-size: 20px; }
    .process-step { gap: 20px; padding: 24px 0; }

    .why { padding: 72px 20px; }
    .why-grid { grid-template-columns: 1fr 1fr; margin-top: 40px; }
    .why-card { padding: 24px 18px; }
    .why-icon { width: 40px; height: 40px; font-size: 16px; margin-bottom: 14px; }
    .why-title { font-size: 15px; }
    .why-desc { font-size: 12px; }

    .cta-section { padding: 72px 24px; }
    .cta-section p br { display: none; }
    .contact-links { flex-direction: column; gap: 16px; align-items: center; margin-top: 36px; }

    footer { padding: 28px 24px; flex-direction: column; gap: 10px; text-align: center; }
  }

  @media (max-width: 390px) {
    h1 { font-size: 38px; }
    .why-grid { grid-template-columns: 1fr; }
    .hero-stats-inline { flex-direction: column; border-top: none; padding-top: 24px; }
    .hero-stats-inline .stat {
      border-right: none; border-bottom: 1px solid rgba(201,168,76,0.15);
      padding: 0 0 16px;
    }
    .hero-stats-inline .stat:last-child { border-bottom: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Abman<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#contact" class="nav-cta">Get Started</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Open menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- MOBILE MENU -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#services" class="mlink">Services</a>
  <a href="#process" class="mlink">Process</a>
  <a href="#why" class="mlink">Why Us</a>
  <a href="#contact" class="mlink mobile-cta">Get Started</a>
  <div class="mob-contacts">
    <a href="https://wa.me/94772136757" class="mlink">+94 77 213 6757</a>
    <a href="mailto:dropafy@gmail.com" class="mlink">dropafy@gmail.com</a>
  </div>
</div>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-line"></div>
  <div class="hero-content">
    <div class="hero-tag">Abman Media — Digital Growth Agency</div>
    <h1>Your Business<br>Deserves to <em>Shine</em><br>Online.</h1>
    <p class="hero-sub">We build stunning websites, run powerful ads, create scroll-stopping content, and set up your Google presence — everything you need to grow.</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">Get a Free Demo</a>
      <a href="#services" class="btn-ghost">See our services</a>
    </div>
    <div class="hero-stats-inline">
      <div class="stat"><div class="stat-num">48h</div><div class="stat-label">Delivery</div></div>
      <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Mobile ready</div></div>
      <div class="stat"><div class="stat-num">4×</div><div class="stat-label">Customers</div></div>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat"><div class="stat-num">48h</div><div class="stat-label">Delivery time</div></div>
    <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Mobile ready</div></div>
    <div class="stat"><div class="stat-num">4×</div><div class="stat-label">More customers</div></div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-section">
  <div class="marquee-track">
    <div class="marquee-item">Websites</div>
    <div class="marquee-item">Google SEO</div>
    <div class="marquee-item">Paid Ads</div>
    <div class="marquee-item">Content Creation</div>
    <div class="marquee-item">Social Media</div>
    <div class="marquee-item">Brand Design</div>
    <div class="marquee-item">Websites</div>
    <div class="marquee-item">Google SEO</div>
    <div class="marquee-item">Paid Ads</div>
    <div class="marquee-item">Content Creation</div>
    <div class="marquee-item">Social Media</div>
    <div class="marquee-item">Brand Design</div>
  </div>
</div>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="section-header reveal">
    <div>
      <div class="section-tag">What we do</div>
      <h2>Everything Your<br>Business Needs</h2>
    </div>
    <p class="section-desc">From a beautiful website to full digital marketing — we handle it all so you can focus on running your business.</p>
  </div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-num">01</div>
      <div class="service-icon">🌐</div>
      <div class="service-title">Website Design</div>
      <p class="service-desc">A fast, beautiful, mobile-ready website that makes your business look professional and trustworthy from day one.</p>
      <div class="service-price">Starting from $120</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">02</div>
      <div class="service-icon">📍</div>
      <div class="service-title">Google SEO Setup</div>
      <p class="service-desc">Get found on Google when locals search for your service. We set up and optimise your Google Business profile completely.</p>
      <div class="service-price">Starting from $60</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">03</div>
      <div class="service-icon">📣</div>
      <div class="service-title">Paid Ads</div>
      <p class="service-desc">Facebook and Instagram ads that bring real paying customers to your door — not just likes.</p>
      <div class="service-price">Starting from $80/mo</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">04</div>
      <div class="service-icon">🎥</div>
      <div class="service-title">Content Creation</div>
      <p class="service-desc">Professional photos, videos, and social posts that represent your brand and keep customers engaged every week.</p>
      <div class="service-price">Starting from $70/mo</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">05</div>
      <div class="service-icon">📈</div>
      <div class="service-title">Social Media Management</div>
      <p class="service-desc">We manage your Instagram and Facebook — posting, replying, growing your following while you focus on your business.</p>
      <div class="service-price">Starting from $90/mo</div>
    </div>
    <div class="service-card reveal">
      <div class="service-num">06</div>
      <div class="service-icon">⚡</div>
      <div class="service-title">Full Growth Package</div>
      <p class="service-desc">Website + SEO + ads + content + social — everything handled by us. Maximum growth, minimum hassle for you.</p>
      <div class="service-price">Bundle from $250/mo</div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section class="process" id="process">
  <div class="reveal">
    <div class="section-tag">How it works</div>
    <h2>From Zero to Online<br>in 48 Hours</h2>
  </div>
  <div class="process-grid">
    <div class="process-steps">
      <div class="process-step reveal">
        <div class="step-num">01</div>
        <div class="step-content">
          <h3>Free Demo First</h3>
          <p>We build a free preview of your new website before you pay a single cent. You see the result before committing.</p>
        </div>
      </div>
      <div class="process-step reveal">
        <div class="step-num">02</div>
        <div class="step-content">
          <h3>You Approve &amp; We Build</h3>
          <p>Once you love the demo, we finalise everything — full website, SEO setup, all pages built to your brand.</p>
        </div>
      </div>
      <div class="process-step reveal">
        <div class="step-num">03</div>
        <div class="step-content">
          <h3>Go Live in 48 Hours</h3>
          <p>Your site is live and customers can find you within 2 days. We handle all the technical setup for you.</p>
        </div>
      </div>
      <div class="process-step reveal">
        <div class="step-num">04</div>
        <div class="step-content">
          <h3>Grow on Autopilot</h3>
          <p>We keep running your ads, content, and social so your business keeps growing every single month.</p>
        </div>
      </div>
    </div>
    <div class="process-visual reveal">
      <div class="visual-phone">
        <div class="phone-notch"></div>
        <div class="phone-screen">
          <div class="phone-bar short"></div>
          <div class="phone-bar"></div>
          <div class="phone-bar img"></div>
          <div class="phone-bar short"></div>
          <div class="phone-bar"></div>
          <div class="phone-bar gold"></div>
        </div>
      </div>
      <div class="visual-badge">Live in 48h</div>
      <div class="visual-badge2">
        <div class="badge2-num">4×</div>
        <div style="font-size:11px;color:rgba(245,242,236,0.5);margin-top:2px;">More reach</div>
      </div>
    </div>
  </div>
</section>

<!-- WHY -->
<section class="why" id="why">
  <div class="reveal" style="text-align:center">
    <div class="section-tag" style="text-align:center">Why Abman Media</div>
    <h2>Built for Small<br>Businesses Like Yours</h2>
  </div>
  <div class="why-grid">
    <div class="why-card reveal">
      <div class="why-icon">🎯</div>
      <div class="why-title">Results First</div>
      <p class="why-desc">We don't just make things look good. Every decision is made to bring you more customers and more revenue.</p>
    </div>
    <div class="why-card reveal">
      <div class="why-icon">💬</div>
      <div class="why-title">Always Reachable</div>
      <p class="why-desc">WhatsApp us anytime. Real humans who respond fast — not a support ticket system that takes days.</p>
    </div>
    <div class="why-card reveal">
      <div class="why-icon">💰</div>
      <div class="why-title">Honest Pricing</div>
      <p class="why-desc">No hidden fees. No confusing contracts. Clear prices, clear deliverables, and you own everything we build.</p>
    </div>
    <div class="why-card reveal">
      <div class="why-icon">🚀</div>
      <div class="why-title">Fast Delivery</div>
      <p class="why-desc">Most agencies take weeks. We go from demo to live website in 48 hours because your time is money.</p>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="contact">
  <h2 class="reveal">Ready to Grow<br>Your Business?</h2>
  <p class="reveal">We'll build you a free demo website — no payment, no commitment. Just message us and see your business transformed.</p>
  <div class="cta-actions reveal">
    <a href="https://wa.me/94772136757?text=Hi%20Abman%20Media%2C%20I%27d%20like%20a%20free%20website%20demo" class="btn-primary" target="_blank">WhatsApp Us Now</a>
  </div>
  <div class="contact-links reveal">
    <a href="mailto:dropafy@gmail.com" class="contact-link">
      <span>✉</span> dropafy@gmail.com
    </a>
    <a href="https://instagram.com/abmanmedia" class="contact-link" target="_blank">
      <span>📸</span> @abmanmedia
    </a>
    <a href="https://wa.me/94772136757" class="contact-link" target="_blank">
      <span>💬</span> +94 77 213 6757
    </a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Abman<span>.</span>Media</div>
  <div class="footer-copy">© 2025 Abman Media. All rights reserved.</div>
</footer>

<script>
  const btn = document.getElementById('hamburger');
  const menu = document.getElementById('mobileMenu');

  btn.addEventListener('click', () => {
    const isOpen = menu.classList.contains('open');
    if (isOpen) {
      menu.classList.remove('open');
      btn.classList.remove('open');
      document.body.style.overflow = '';
      setTimeout(() => { menu.style.display = 'none'; }, 300);
    } else {
      menu.style.display = 'flex';
      requestAnimationFrame(() => {
        requestAnimationFrame(() => { menu.classList.add('open'); });
      });
      btn.classList.add('open');
      document.body.style.overflow = 'hidden';
    }
  });

  document.querySelectorAll('.mlink').forEach(link => {
    link.addEventListener('click', () => {
      menu.classList.remove('open');
      btn.classList.remove('open');
      document.body.style.overflow = '';
      setTimeout(() => { menu.style.display = 'none'; }, 300);
    });
  });

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.08 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
