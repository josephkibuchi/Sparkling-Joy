<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sparkling Joy Co. Ltd – Expert Cleaning Services</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #00a651;
    --green-dark: #007a3d;
    --green-light: #e6f7ee;
    --blue: #00aaff;
    --blue-light: #e0f4ff;
    --white: #ffffff;
    --off-white: #f7fdf9;
    --dark: #0a1f14;
    --gray: #5c7a68;
    --light-gray: #d4e8dd;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--white);
    color: var(--dark);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 18px 6vw;
    background: rgba(255,255,255,0.92);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(0,166,81,0.12);
    animation: slideDown 0.6s ease both;
  }
  @keyframes slideDown { from { transform: translateY(-100%); opacity: 0; } to { transform: translateY(0); opacity: 1; } }

  .nav-logo {
    display: flex; align-items: center; gap: 12px;
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem; font-weight: 700; color: var(--green-dark);
    text-decoration: none;
  }
  .nav-logo-icon {
    width: 44px; height: 44px; border-radius: 50%;
    border: 2px solid var(--green);
    display: grid; place-items: center;
    font-size: 1.1rem; font-weight: 900; color: var(--green);
    background: var(--green-light);
  }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--gray); font-size: 0.9rem; font-weight: 500; transition: color 0.2s; }
  .nav-links a:hover { color: var(--green); }
  .nav-cta {
    background: var(--green); color: white; border: none; cursor: pointer;
    padding: 11px 24px; border-radius: 50px; font-size: 0.88rem; font-weight: 600;
    font-family: 'DM Sans', sans-serif;
    transition: background 0.2s, transform 0.15s;
  }
  .nav-cta:hover { background: var(--green-dark); transform: translateY(-1px); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr; align-items: center;
    padding: 120px 6vw 80px;
    background: var(--off-white);
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; top: -120px; right: -80px;
    width: 580px; height: 580px; border-radius: 50%;
    background: radial-gradient(circle, rgba(0,166,81,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute; bottom: -80px; left: 10%;
    width: 320px; height: 320px; border-radius: 50%;
    background: radial-gradient(circle, rgba(0,170,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-text { position: relative; z-index: 2; animation: fadeUp 0.8s 0.2s ease both; }
  @keyframes fadeUp { from { transform: translateY(40px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--green-light); color: var(--green-dark);
    padding: 6px 16px; border-radius: 50px; font-size: 0.8rem; font-weight: 600;
    margin-bottom: 24px; letter-spacing: 0.04em; text-transform: uppercase;
  }
  .hero-badge span { width: 7px; height: 7px; background: var(--green); border-radius: 50%; display: inline-block; animation: pulse 1.8s infinite; }
  @keyframes pulse { 0%,100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(0.7); } }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.6rem, 4.5vw, 4rem);
    font-weight: 900; line-height: 1.1;
    color: var(--dark); margin-bottom: 22px;
  }
  .hero h1 .accent { color: var(--green); }
  .hero h1 .accent-blue { color: var(--blue); }

  .hero-sub {
    font-size: 1.05rem; color: var(--gray); line-height: 1.7;
    max-width: 460px; margin-bottom: 36px;
  }
  .hero-tagline {
    font-style: italic; font-size: 0.85rem; color: var(--green-dark);
    margin-bottom: 10px; font-weight: 500;
  }

  .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; margin-bottom: 48px; }
  .btn-primary {
    background: var(--green); color: white; border: none; cursor: pointer;
    padding: 15px 32px; border-radius: 50px; font-size: 1rem; font-weight: 600;
    font-family: 'DM Sans', sans-serif; text-decoration: none;
    display: inline-flex; align-items: center; gap: 8px;
    transition: all 0.2s; box-shadow: 0 6px 24px rgba(0,166,81,0.28);
  }
  .btn-primary:hover { background: var(--green-dark); transform: translateY(-2px); box-shadow: 0 10px 32px rgba(0,166,81,0.35); }
  .btn-secondary {
    background: transparent; color: var(--green-dark); border: 2px solid var(--green);
    cursor: pointer; padding: 13px 28px; border-radius: 50px;
    font-size: 1rem; font-weight: 600; font-family: 'DM Sans', sans-serif;
    text-decoration: none; display: inline-flex; align-items: center; gap: 8px;
    transition: all 0.2s;
  }
  .btn-secondary:hover { background: var(--green-light); }

  .hero-stats { display: flex; gap: 32px; }
  .stat { }
  .stat-num { font-family: 'Playfair Display', serif; font-size: 1.8rem; font-weight: 700; color: var(--green-dark); }
  .stat-label { font-size: 0.78rem; color: var(--gray); font-weight: 500; }

  .hero-visual {
    position: relative; z-index: 2; display: flex; justify-content: center; align-items: center;
    animation: fadeUp 0.8s 0.5s ease both;
  }
  .hero-card-main {
    background: white; border-radius: 24px;
    box-shadow: 0 20px 60px rgba(0,0,0,0.1);
    padding: 0; overflow: hidden; width: 340px;
    border: 1px solid var(--light-gray);
  }
  .hero-card-img {
    width: 100%; height: 220px;
    background: linear-gradient(135deg, var(--green) 0%, var(--blue) 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem; position: relative; overflow: hidden;
  }
  .hero-card-img::before {
    content: '✦';
    position: absolute; top: 12px; right: 16px;
    font-size: 1.2rem; color: rgba(255,255,255,0.4);
  }
  .hero-card-body { padding: 24px; }
  .hero-card-body h3 { font-family: 'Playfair Display', serif; font-size: 1.1rem; margin-bottom: 8px; }
  .hero-card-body p { font-size: 0.85rem; color: var(--gray); line-height: 1.5; }

  .float-chip {
    position: absolute; background: white; border-radius: 16px;
    padding: 12px 18px; box-shadow: 0 8px 30px rgba(0,0,0,0.12);
    display: flex; align-items: center; gap: 10px; font-size: 0.82rem; font-weight: 600;
    border: 1px solid var(--light-gray); animation: float 3s ease-in-out infinite;
  }
  @keyframes float { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }
  .chip-1 { top: 20px; right: -20px; animation-delay: 0s; }
  .chip-2 { bottom: 40px; left: -30px; animation-delay: 1.5s; }
  .chip-icon { font-size: 1.3rem; }
  .chip-text span { display: block; font-size: 0.7rem; font-weight: 400; color: var(--gray); }

  /* ── SERVICES ── */
  .services {
    padding: 100px 6vw;
    background: white;
  }
  .section-header { text-align: center; margin-bottom: 60px; }
  .section-tag {
    display: inline-block; background: var(--green-light); color: var(--green-dark);
    padding: 5px 16px; border-radius: 50px; font-size: 0.78rem; font-weight: 600;
    letter-spacing: 0.06em; text-transform: uppercase; margin-bottom: 16px;
  }
  .section-header h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 2.8rem); font-weight: 900;
    color: var(--dark); margin-bottom: 16px;
  }
  .section-header p { color: var(--gray); font-size: 1rem; max-width: 520px; margin: 0 auto; line-height: 1.7; }

  .services-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 24px;
  }
  .service-card {
    background: var(--off-white); border-radius: 20px; padding: 32px 28px;
    border: 1px solid var(--light-gray); transition: all 0.3s;
    position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, var(--green), var(--blue));
    transform: scaleX(0); transform-origin: left; transition: transform 0.3s;
  }
  .service-card:hover { transform: translateY(-6px); box-shadow: 0 16px 40px rgba(0,166,81,0.12); border-color: var(--green); }
  .service-card:hover::before { transform: scaleX(1); }
  .service-icon { font-size: 2.4rem; margin-bottom: 18px; }
  .service-card h3 { font-family: 'Playfair Display', serif; font-size: 1.15rem; margin-bottom: 10px; color: var(--dark); }
  .service-card p { font-size: 0.88rem; color: var(--gray); line-height: 1.65; }
  .service-link { display: inline-flex; align-items: center; gap: 5px; margin-top: 16px; color: var(--green); font-size: 0.85rem; font-weight: 600; text-decoration: none; }
  .service-link:hover { gap: 9px; }

  /* ── WHY US ── */
  .why {
    padding: 100px 6vw;
    background: var(--dark);
    color: white; position: relative; overflow: hidden;
  }
  .why::before {
    content: '';
    position: absolute; top: -100px; right: -100px;
    width: 500px; height: 500px; border-radius: 50%;
    background: radial-gradient(circle, rgba(0,166,81,0.15) 0%, transparent 70%);
  }
  .why-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; position: relative; z-index: 2; }
  .why-text .section-tag { background: rgba(0,166,81,0.2); color: #5de8a0; }
  .why-text h2 { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 3vw, 2.6rem); font-weight: 900; color: white; margin-bottom: 20px; line-height: 1.15; }
  .why-text p { color: rgba(255,255,255,0.65); line-height: 1.8; margin-bottom: 32px; }

  .why-features { display: grid; gap: 20px; }
  .why-feat {
    display: flex; gap: 16px; align-items: flex-start;
    background: rgba(255,255,255,0.05); border-radius: 14px; padding: 20px;
    border: 1px solid rgba(255,255,255,0.08); transition: all 0.2s;
  }
  .why-feat:hover { background: rgba(0,166,81,0.1); border-color: rgba(0,166,81,0.3); }
  .why-feat-icon { font-size: 1.6rem; flex-shrink: 0; }
  .why-feat h4 { font-weight: 600; margin-bottom: 4px; font-size: 0.95rem; }
  .why-feat p { font-size: 0.82rem; color: rgba(255,255,255,0.55); line-height: 1.5; margin: 0; }

  /* ── TESTIMONIALS ── */
  .testimonials { padding: 100px 6vw; background: var(--green-light); }
  .testi-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; margin-top: 50px; }
  .testi-card {
    background: white; border-radius: 20px; padding: 30px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.06); border: 1px solid var(--light-gray);
  }
  .testi-stars { color: #f5a623; font-size: 1rem; margin-bottom: 14px; }
  .testi-card p { font-size: 0.9rem; color: var(--dark); line-height: 1.7; font-style: italic; margin-bottom: 20px; }
  .testi-author { display: flex; align-items: center; gap: 12px; }
  .testi-avatar {
    width: 42px; height: 42px; border-radius: 50%;
    background: linear-gradient(135deg, var(--green), var(--blue));
    display: grid; place-items: center; color: white; font-weight: 700; font-size: 1rem;
  }
  .testi-name { font-weight: 600; font-size: 0.88rem; }
  .testi-role { font-size: 0.78rem; color: var(--gray); }

  /* ── BIBLE VERSE BANNER ── */
  .verse-banner {
    background: linear-gradient(135deg, var(--green-dark), var(--green));
    padding: 60px 6vw; text-align: center; color: white;
  }
  .verse-banner blockquote {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.3rem, 2.5vw, 1.8rem); font-weight: 700;
    max-width: 680px; margin: 0 auto 12px; line-height: 1.4;
  }
  .verse-banner cite { font-size: 0.9rem; opacity: 0.8; font-style: normal; }

  /* ── CONTACT ── */
  .contact { padding: 100px 6vw; background: white; }
  .contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .contact-info h2 { font-family: 'Playfair Display', serif; font-size: clamp(1.8rem, 2.5vw, 2.4rem); font-weight: 900; margin-bottom: 20px; }
  .contact-info p { color: var(--gray); line-height: 1.8; margin-bottom: 32px; }
  .contact-item { display: flex; gap: 14px; align-items: center; margin-bottom: 20px; }
  .contact-item-icon {
    width: 46px; height: 46px; border-radius: 12px;
    background: var(--green-light); display: grid; place-items: center;
    font-size: 1.2rem; flex-shrink: 0;
  }
  .contact-item-text strong { display: block; font-size: 0.85rem; color: var(--dark); font-weight: 600; }
  .contact-item-text span { font-size: 0.82rem; color: var(--gray); }

  .contact-form { background: var(--off-white); border-radius: 24px; padding: 36px; border: 1px solid var(--light-gray); }
  .contact-form h3 { font-family: 'Playfair Display', serif; font-size: 1.3rem; margin-bottom: 24px; }
  .form-group { margin-bottom: 18px; }
  .form-group label { display: block; font-size: 0.82rem; font-weight: 600; margin-bottom: 6px; color: var(--dark); }
  .form-group input, .form-group select, .form-group textarea {
    width: 100%; padding: 12px 16px; border-radius: 10px;
    border: 1.5px solid var(--light-gray); background: white;
    font-family: 'DM Sans', sans-serif; font-size: 0.9rem; color: var(--dark);
    transition: border-color 0.2s; outline: none;
  }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus { border-color: var(--green); }
  .form-group textarea { height: 110px; resize: vertical; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .form-submit {
    width: 100%; background: var(--green); color: white; border: none; cursor: pointer;
    padding: 14px; border-radius: 50px; font-size: 1rem; font-weight: 600;
    font-family: 'DM Sans', sans-serif; transition: all 0.2s;
    box-shadow: 0 6px 20px rgba(0,166,81,0.25);
  }
  .form-submit:hover { background: var(--green-dark); transform: translateY(-1px); }

  /* ── FOOTER ── */
  footer {
    background: var(--dark); color: rgba(255,255,255,0.7);
    padding: 60px 6vw 30px;
  }
  .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 60px; margin-bottom: 48px; }
  .footer-brand .nav-logo { color: white; margin-bottom: 16px; display: inline-flex; }
  .footer-brand p { font-size: 0.85rem; line-height: 1.8; max-width: 280px; }
  .footer-col h4 { color: white; font-size: 0.9rem; font-weight: 600; margin-bottom: 18px; }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 10px; }
  .footer-col ul li a { color: rgba(255,255,255,0.6); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
  .footer-col ul li a:hover { color: var(--green); }
  .footer-bottom { border-top: 1px solid rgba(255,255,255,0.1); padding-top: 24px; display: flex; justify-content: space-between; align-items: center; font-size: 0.8rem; }
  .footer-bottom a { color: var(--green); text-decoration: none; }

  /* ── RESPONSIVE ── */
  @media (max-width: 860px) {
    .hero { grid-template-columns: 1fr; padding-top: 100px; text-align: center; }
    .hero-visual { display: none; }
    .hero-actions { justify-content: center; }
    .hero-stats { justify-content: center; }
    .why-inner { grid-template-columns: 1fr; gap: 40px; }
    .contact-inner { grid-template-columns: 1fr; }
    .footer-grid { grid-template-columns: 1fr; gap: 32px; }
    .nav-links { display: none; }
    .form-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <div class="nav-logo-icon">SPJ</div>
    Sparkling Joy
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#testimonials">Reviews</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="nav-cta" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Book a Cleaning</button>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-text">
    <div class="hero-badge"><span></span> Nairobi's Trusted Cleaning Experts</div>
    <h1>A <span class="accent">Cleaner</span> Space,<br>A <span class="accent-blue">Brighter</span> Life.</h1>
    <p class="hero-sub">Professional home, office, and commercial cleaning services delivered with care, precision, and eco-conscious practices.</p>
    <p class="hero-tagline">✦ "Our responsibility to take care for the earth" – Gen 2:15</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">📅 Schedule a Cleaning</a>
      <a href="https://www.sparklingjoy.com" target="_blank" class="btn-secondary">🌐 Visit Website</a>
    </div>
    <div class="hero-stats">
      <div class="stat">
        <div class="stat-num">500+</div>
        <div class="stat-label">Happy Clients</div>
      </div>
      <div class="stat">
        <div class="stat-num">5+</div>
        <div class="stat-label">Services Offered</div>
      </div>
      <div class="stat">
        <div class="stat-num">100%</div>
        <div class="stat-label">Satisfaction</div>
      </div>
    </div>
  </div>

  <div class="hero-visual">
    <div style="position:relative;">
      <div class="hero-card-main">
        <div class="hero-card-img">🧹✨</div>
        <div class="hero-card-body">
          <h3>Expert Cleaning Teams</h3>
          <p>Trained professionals equipped with eco-friendly products for every cleaning challenge.</p>
        </div>
      </div>
      <div class="float-chip chip-1">
        <div class="chip-icon">🌿</div>
        <div class="chip-text">Eco-Friendly<span>Green products only</span></div>
      </div>
      <div class="float-chip chip-2">
        <div class="chip-icon">⭐</div>
        <div class="chip-text">Top Rated<span>Trusted since day one</span></div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="section-header">
    <div class="section-tag">What We Do</div>
    <h2>Comprehensive Cleaning Solutions</h2>
    <p>From homes to offices, carpets to gardens — we've got every corner covered with expert care.</p>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🏠</div>
      <h3>Home Cleaning</h3>
      <p>Thorough, reliable residential cleaning tailored to your schedule. We treat your home like our own.</p>
      <a href="#contact" class="service-link">Book now →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🏢</div>
      <h3>Office Cleaning</h3>
      <p>Keep your workspace spotless and professional. We work around your hours for zero disruption.</p>
      <a href="#contact" class="service-link">Book now →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🦟</div>
      <h3>Fumigation</h3>
      <p>Safe, effective fumigation to eliminate pests and protect your environment from infestation.</p>
      <a href="#contact" class="service-link">Book now →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🪞</div>
      <h3>Carpet Cleaning</h3>
      <p>Deep extraction cleaning that lifts dirt, stains, and allergens for fresher, cleaner carpets.</p>
      <a href="#contact" class="service-link">Book now →</a>
    </div>
    <div class="service-card">
      <div class="service-icon">🌱</div>
      <h3>Landscaping</h3>
      <p>Beautiful, well-maintained outdoor spaces. Mowing, trimming, and green care done right.</p>
      <a href="#contact" class="service-link">Book now →</a>
    </div>
    <div class="service-card" style="background: linear-gradient(135deg, var(--green) 0%, #00c970 100%); border-color: transparent;">
      <div class="service-icon" style="font-size:2rem;">🎯</div>
      <h3 style="color:white;">Custom Packages</h3>
      <p style="color:rgba(255,255,255,0.85);">Need something specific? We craft bespoke cleaning plans for unique spaces and requirements.</p>
      <a href="#contact" class="service-link" style="color:white;">Talk to us →</a>
    </div>
  </div>
</section>

<!-- WHY US -->
<section class="why" id="why">
  <div class="why-inner">
    <div class="why-text">
      <div class="section-tag">Why Sparkling Joy</div>
      <h2>Cleaning with<br>Purpose & Pride</h2>
      <p>We believe cleanliness is more than aesthetics — it's a responsibility. Rooted in the ethos of caring for our earth and the people who inhabit it, every job we do reflects our commitment to excellence.</p>
      <a href="#contact" class="btn-primary">Get a Free Quote</a>
    </div>
    <div class="why-features">
      <div class="why-feat">
        <div class="why-feat-icon">🌍</div>
        <div>
          <h4>Eco-Conscious Approach</h4>
          <p>We use environmentally responsible products that are safe for your family, pets, and the planet.</p>
        </div>
      </div>
      <div class="why-feat">
        <div class="why-feat-icon">👔</div>
        <div>
          <h4>Trained & Vetted Teams</h4>
          <p>All our cleaning professionals are carefully trained, uniformed, and background-checked.</p>
        </div>
      </div>
      <div class="why-feat">
        <div class="why-feat-icon">⏰</div>
        <div>
          <h4>Flexible Scheduling</h4>
          <p>Book at a time that works for you — morning, evening, weekday, or weekend.</p>
        </div>
      </div>
      <div class="why-feat">
        <div class="why-feat-icon">💰</div>
        <div>
          <h4>Exciting Offers Available</h4>
          <p>Schedule your first cleaning and unlock exclusive deals crafted just for new customers.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
  <div class="section-header">
    <div class="section-tag">Client Reviews</div>
    <h2>What Our Clients Say</h2>
    <p>Real results, real smiles. Here's what Nairobi says about Sparkling Joy.</p>
  </div>
  <div class="testi-grid">
    <div class="testi-card">
      <div class="testi-stars">★★★★★</div>
      <p>"The team was professional, thorough, and left our office spotless. We've booked them monthly ever since!"</p>
      <div class="testi-author">
        <div class="testi-avatar">A</div>
        <div><div class="testi-name">Amina K.</div><div class="testi-role">Office Manager, Westlands</div></div>
      </div>
    </div>
    <div class="testi-card">
      <div class="testi-stars">★★★★★</div>
      <p>"Incredible carpet cleaning — stains I thought were permanent are completely gone. Highly recommend their team."</p>
      <div class="testi-author">
        <div class="testi-avatar">J</div>
        <div><div class="testi-name">James M.</div><div class="testi-role">Homeowner, Karen</div></div>
      </div>
    </div>
    <div class="testi-card">
      <div class="testi-stars">★★★★★</div>
      <p>"Fast, reliable, and they genuinely care about the environment. The fumigation service saved us from a major pest problem."</p>
      <div class="testi-author">
        <div class="testi-avatar">F</div>
        <div><div class="testi-name">Faith W.</div><div class="testi-role">Restaurant Owner, Kileleshwa</div></div>
      </div>
    </div>
  </div>
</section>

<!-- VERSE BANNER -->
<div class="verse-banner">
  <blockquote>"The Lord God took the man and put him in the Garden of Eden to work it and take care of it."</blockquote>
  <cite>— Genesis 2:15 · The heartbeat of everything we do at Sparkling Joy</cite>
</div>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="contact-info">
      <div class="section-tag">Get In Touch</div>
      <h2>Let's Make Your Space Sparkle</h2>
      <p>Ready to experience the Sparkling Joy difference? Reach out to schedule a cleaning or get a custom quote — we'd love to hear from you.</p>
      <div class="contact-item">
        <div class="contact-item-icon">📞</div>
        <div class="contact-item-text">
          <strong>Call Us</strong>
          <span>0722 472 124 / 0722 625 821</span>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">🌐</div>
        <div class="contact-item-text">
          <strong>Website</strong>
          <span><a href="https://www.sparklingjoy.com" style="color:var(--green)">www.sparklingjoy.com</a></span>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">📍</div>
        <div class="contact-item-text">
          <strong>Location</strong>
          <span>Nairobi, Kenya</span>
        </div>
      </div>
    </div>
    <div class="contact-form">
      <h3>Book a Cleaning</h3>
      <div class="form-row">
        <div class="form-group">
          <label>First Name</label>
          <input type="text" placeholder="Jane">
        </div>
        <div class="form-group">
          <label>Last Name</label>
          <input type="text" placeholder="Doe">
        </div>
      </div>
      <div class="form-group">
        <label>Phone Number</label>
        <input type="tel" placeholder="0700 000 000">
      </div>
      <div class="form-group">
        <label>Service Needed</label>
        <select>
          <option value="">Select a service...</option>
          <option>Home Cleaning</option>
          <option>Office Cleaning</option>
          <option>Fumigation</option>
          <option>Carpet Cleaning</option>
          <option>Landscaping</option>
          <option>Custom Package</option>
        </select>
      </div>
      <div class="form-group">
        <label>Message / Details</label>
        <textarea placeholder="Tell us about your space and what you need..."></textarea>
      </div>
      <button class="form-submit">✨ Submit Request</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <a href="#" class="nav-logo">
        <div class="nav-logo-icon">SPJ</div>
        Sparkling Joy Co. Ltd
      </a>
      <p>Professional cleaning services rooted in care for people and the planet. With you every step of the way.</p>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Home Cleaning</a></li>
        <li><a href="#services">Office Cleaning</a></li>
        <li><a href="#services">Fumigation</a></li>
        <li><a href="#services">Carpet Cleaning</a></li>
        <li><a href="#services">Landscaping</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a href="#why">About Us</a></li>
        <li><a href="#testimonials">Reviews</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="https://www.sparklingjoy.com" target="_blank">Website</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Sparkling Joy Co. Ltd. All rights reserved.</span>
    <span><a href="https://www.sparklingjoy.com">www.sparklingjoy.com</a> · 0722 472 124</span>
  </div>
</footer>

<script>
  // Smooth scroll for all anchor links
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      const target = document.querySelector(a.getAttribute('href'));
      if (target) { e.preventDefault(); target.scrollIntoView({ behavior: 'smooth' }); }
    });
  });

  // Form submission feedback
  document.querySelector('.form-submit').addEventListener('click', function() {
    this.textContent = '✅ Request Sent!';
    this.style.background = 'var(--green-dark)';
    setTimeout(() => { this.textContent = '✨ Submit Request'; this.style.background = ''; }, 3000);
  });

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.style.opacity = '1'; e.target.style.transform = 'translateY(0)'; }
    });
  }, { threshold: 0.15 });
  document.querySelectorAll('.service-card, .why-feat, .testi-card, .contact-item').forEach(el => {
    el.style.opacity = '0'; el.style.transform = 'translateY(24px)';
    el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
