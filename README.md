# <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PixelGuard Foundation | Online Safety Education for Kids & Families</title>
  <meta name="description" content="PixelGuard Foundation is a Spokane-based nonprofit educating children, parents, and gaming communities about online safety and predator prevention." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy: #0D1B2A;
      --navy-mid: #152336;
      --teal: #00C9B1;
      --teal-light: #00E5CC;
      --teal-glow: rgba(0,201,177,0.12);
      --white: #F7F9FC;
      --slate: #4A5568;
      --slate-light: #718096;
      --mint-bg: #E8F8F6;
      --pill-bg: rgba(0,201,177,0.15);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--white);
      color: var(--navy);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      background: rgba(13,27,42,0.95);
      backdrop-filter: blur(12px);
      padding: 0 clamp(1.5rem, 5vw, 4rem);
      height: 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid rgba(0,201,177,0.15);
    }

    .nav-logo {
      display: flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
    }

    .nav-shield {
      display: grid;
      grid-template-columns: repeat(4, 6px);
      grid-template-rows: repeat(5, 6px);
      gap: 1.5px;
    }

    .nav-shield span {
      border-radius: 1px;
      background: var(--teal);
    }

    /* Shield pixel pattern — shield silhouette */
    .nav-shield span:nth-child(1),
    .nav-shield span:nth-child(2),
    .nav-shield span:nth-child(3),
    .nav-shield span:nth-child(4),
    .nav-shield span:nth-child(5),
    .nav-shield span:nth-child(8),
    .nav-shield span:nth-child(9),
    .nav-shield span:nth-child(12),
    .nav-shield span:nth-child(13),
    .nav-shield span:nth-child(16),
    .nav-shield span:nth-child(18),
    .nav-shield span:nth-child(19) { background: var(--teal); }

    .nav-shield span:nth-child(6),
    .nav-shield span:nth-child(7),
    .nav-shield span:nth-child(10),
    .nav-shield span:nth-child(11),
    .nav-shield span:nth-child(14),
    .nav-shield span:nth-child(15),
    .nav-shield span:nth-child(17),
    .nav-shield span:nth-child(20) { background: transparent; }

    .nav-wordmark {
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 1rem;
      color: var(--white);
      letter-spacing: -0.02em;
    }

    .nav-wordmark span { color: var(--teal); }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      color: rgba(247,249,252,0.7);
      text-decoration: none;
      font-size: 0.875rem;
      font-weight: 500;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--teal); }

    .nav-cta {
      background: var(--teal) !important;
      color: var(--navy) !important;
      padding: 0.5rem 1.25rem !important;
      border-radius: 6px;
      font-weight: 600 !important;
      transition: background 0.2s !important;
    }

    .nav-cta:hover { background: var(--teal-light) !important; }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      background: var(--navy);
      display: flex;
      align-items: center;
      padding: 0 clamp(1.5rem, 5vw, 4rem);
      padding-top: 64px;
      position: relative;
      overflow: hidden;
    }

    .hero-grid-bg {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,201,177,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,201,177,0.04) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
    }

    .hero-glow {
      position: absolute;
      top: 10%;
      right: -5%;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(0,201,177,0.12) 0%, transparent 65%);
      pointer-events: none;
    }

    .hero-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    .hero-eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--pill-bg);
      border: 1px solid rgba(0,201,177,0.3);
      border-radius: 100px;
      padding: 0.3rem 0.875rem;
      font-size: 0.75rem;
      font-weight: 600;
      color: var(--teal);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
    }

    .hero-eyebrow::before {
      content: '';
      width: 6px; height: 6px;
      background: var(--teal);
      border-radius: 50%;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(0.8); }
    }

    .hero-headline {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(2.25rem, 4.5vw, 3.5rem);
      font-weight: 700;
      color: var(--white);
      line-height: 1.1;
      letter-spacing: -0.03em;
      margin-bottom: 1.25rem;
    }

    .hero-headline em {
      font-style: normal;
      color: var(--teal);
    }

    .hero-sub {
      color: rgba(247,249,252,0.65);
      font-size: 1.0625rem;
      line-height: 1.7;
      margin-bottom: 2rem;
      max-width: 480px;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn-primary {
      background: var(--teal);
      color: var(--navy);
      padding: 0.8125rem 1.75rem;
      border-radius: 8px;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 0.9375rem;
      text-decoration: none;
      transition: background 0.2s, transform 0.15s;
      display: inline-block;
    }

    .btn-primary:hover { background: var(--teal-light); transform: translateY(-1px); }

    .btn-ghost {
      border: 1px solid rgba(247,249,252,0.25);
      color: rgba(247,249,252,0.85);
      padding: 0.8125rem 1.75rem;
      border-radius: 8px;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 600;
      font-size: 0.9375rem;
      text-decoration: none;
      transition: border-color 0.2s, color 0.2s;
      display: inline-block;
    }

    .btn-ghost:hover { border-color: var(--teal); color: var(--teal); }

    /* Pixel Shield — signature element */
    .pixel-shield {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .shield-grid {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      gap: 4px;
      width: clamp(220px, 28vw, 340px);
      aspect-ratio: 1 / 1.1;
      position: relative;
    }

    .shield-grid .px {
      border-radius: 3px;
      transition: background 0.4s ease;
    }

    /* Teal shield silhouette pixels */
    .px.on { background: var(--teal); }
    /* Inner highlight pixels */
    .px.hi { background: #00ffe8; }
    /* Dark background pixels */
    .px.off { background: rgba(255,255,255,0.04); }
    /* Accent pixels */
    .px.ac { background: rgba(0,201,177,0.3); }

    .shield-label {
      margin-top: 1.25rem;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 1.5rem;
      color: var(--white);
      letter-spacing: -0.02em;
    }

    .shield-label span { color: var(--teal); }

    .shield-tagline {
      font-size: 0.8rem;
      color: rgba(247,249,252,0.4);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-top: 0.4rem;
    }

    /* ── STATS ── */
    #stats {
      background: var(--navy-mid);
      padding: 3rem clamp(1.5rem, 5vw, 4rem);
      border-top: 1px solid rgba(0,201,177,0.1);
      border-bottom: 1px solid rgba(0,201,177,0.1);
    }

    .stats-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
      text-align: center;
    }

    .stat-num {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 700;
      color: var(--teal);
      letter-spacing: -0.03em;
      line-height: 1;
    }

    .stat-label {
      color: rgba(247,249,252,0.55);
      font-size: 0.875rem;
      margin-top: 0.4rem;
      line-height: 1.45;
    }

    /* ── MISSION PILLARS ── */
    #mission {
      padding: 6rem clamp(1.5rem, 5vw, 4rem);
      background: var(--white);
    }

    .section-eyebrow {
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--teal);
      margin-bottom: 0.75rem;
    }

    .section-heading {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(1.75rem, 3.5vw, 2.5rem);
      font-weight: 700;
      color: var(--navy);
      letter-spacing: -0.03em;
      line-height: 1.15;
      margin-bottom: 1rem;
    }

    .section-sub {
      color: var(--slate);
      font-size: 1rem;
      max-width: 520px;
      line-height: 1.7;
      margin-bottom: 3.5rem;
    }

    .pillars {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .pillar-card {
      background: var(--mint-bg);
      border: 1px solid rgba(0,201,177,0.15);
      border-radius: 12px;
      padding: 2rem;
      position: relative;
      overflow: hidden;
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .pillar-card:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 40px rgba(0,201,177,0.1);
    }

    .pillar-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: var(--teal);
    }

    .pillar-icon {
      width: 48px;
      height: 48px;
      background: var(--navy);
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 1.25rem;
      font-size: 1.4rem;
    }

    .pillar-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.1875rem;
      font-weight: 700;
      color: var(--navy);
      margin-bottom: 0.625rem;
      letter-spacing: -0.01em;
    }

    .pillar-desc {
      color: var(--slate);
      font-size: 0.9375rem;
      line-height: 1.65;
    }

    /* ── ABOUT / FOUNDER ── */
    #about {
      padding: 6rem clamp(1.5rem, 5vw, 4rem);
      background: var(--navy);
      position: relative;
      overflow: hidden;
    }

    #about::before {
      content: '';
      position: absolute;
      bottom: -20%;
      left: -10%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(0,201,177,0.08) 0%, transparent 65%);
      pointer-events: none;
    }

    .about-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    #about .section-heading { color: var(--white); }
    #about .section-sub { color: rgba(247,249,252,0.6); }
    #about .section-eyebrow { margin-bottom: 0.75rem; }

    .founder-quote {
      border-left: 3px solid var(--teal);
      padding-left: 1.25rem;
      margin: 2rem 0;
    }

    .founder-quote p {
      color: rgba(247,249,252,0.8);
      font-size: 1.05rem;
      line-height: 1.7;
      font-style: italic;
    }

    .founder-byline {
      margin-top: 0.75rem;
      color: var(--teal);
      font-size: 0.875rem;
      font-weight: 600;
    }

    .about-callouts {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    .callout-box {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(0,201,177,0.15);
      border-radius: 10px;
      padding: 1.25rem;
    }

    .callout-box strong {
      display: block;
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.5rem;
      color: var(--teal);
      font-weight: 700;
      line-height: 1;
      letter-spacing: -0.02em;
      margin-bottom: 0.3rem;
    }

    .callout-box span {
      font-size: 0.8125rem;
      color: rgba(247,249,252,0.5);
    }

    /* ── CONTACT / AUDIENCES ── */
    #contact {
      padding: 6rem clamp(1.5rem, 5vw, 4rem);
      background: var(--white);
    }

    .contact-inner {
      max-width: 1100px;
      margin: 0 auto;
    }

    .contact-header { margin-bottom: 3rem; }

    .audience-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.25rem;
      margin-bottom: 3rem;
    }

    .audience-card {
      border: 1px solid rgba(13,27,42,0.12);
      border-radius: 12px;
      padding: 1.75rem;
      transition: border-color 0.2s, box-shadow 0.2s;
      text-decoration: none;
      display: block;
      color: inherit;
    }

    .audience-card:hover {
      border-color: var(--teal);
      box-shadow: 0 8px 32px rgba(0,201,177,0.1);
    }

    .audience-icon {
      font-size: 1.75rem;
      margin-bottom: 0.875rem;
    }

    .audience-title {
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 1rem;
      color: var(--navy);
      margin-bottom: 0.5rem;
      letter-spacing: -0.01em;
    }

    .audience-desc {
      font-size: 0.875rem;
      color: var(--slate);
      line-height: 1.6;
    }

    .audience-link {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      margin-top: 0.875rem;
      font-size: 0.8125rem;
      font-weight: 600;
      color: var(--teal);
    }

    .contact-direct {
      background: var(--navy);
      border-radius: 12px;
      padding: 2.5rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 2rem;
      flex-wrap: wrap;
    }

    .contact-direct-text h3 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 0.375rem;
    }

    .contact-direct-text p {
      color: rgba(247,249,252,0.55);
      font-size: 0.9rem;
    }

    /* ── FOOTER ── */
    footer {
      background: var(--navy);
      border-top: 1px solid rgba(0,201,177,0.1);
      padding: 2.5rem clamp(1.5rem, 5vw, 4rem);
    }

    .footer-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .footer-brand {
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      color: var(--white);
      font-size: 0.9375rem;
    }

    .footer-brand span { color: var(--teal); }

    .footer-meta {
      font-size: 0.8rem;
      color: rgba(247,249,252,0.35);
    }

    .footer-meta a {
      color: rgba(247,249,252,0.4);
      text-decoration: none;
    }

    .footer-meta a:hover { color: var(--teal); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      .hero-inner, .about-inner { grid-template-columns: 1fr; }
      .pixel-shield { display: none; }
      .stats-inner { grid-template-columns: 1fr; gap: 1.5rem; }
      .pillars { grid-template-columns: 1fr; }
      .audience-grid { grid-template-columns: 1fr; }
      .about-callouts { grid-template-columns: 1fr 1fr; }
      nav .nav-links { display: none; }
    }

    @media (prefers-reduced-motion: reduce) {
      .hero-eyebrow::before { animation: none; }
      * { transition: none !important; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#hero" class="nav-logo">
    <div class="nav-shield" aria-hidden="true">
      <span></span><span></span><span></span><span></span>
      <span></span><span></span><span></span><span></span>
      <span></span><span></span><span></span><span></span>
      <span></span><span></span><span></span><span></span>
      <span></span><span></span><span></span><span></span>
    </div>
    <span class="nav-wordmark"><span>Pixel</span>Guard Foundation</span>
  </a>
  <ul class="nav-links">
    <li><a href="#mission">Mission</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Get Involved</a></li>
    <li><a href="mailto:hello@pixelguard.org" class="nav-cta">Contact Us</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-grid-bg" aria-hidden="true"></div>
  <div class="hero-glow" aria-hidden="true"></div>
  <div class="hero-inner">
    <div class="hero-content">
      <div class="hero-eyebrow">Spokane, WA · Nonprofit Organization</div>
      <h1 class="hero-headline">
        Online safety starts <em>before</em> danger finds them.
      </h1>
      <p class="hero-sub">
        PixelGuard Foundation equips children, parents, and gaming communities with real knowledge to recognize and resist online predators — before it's too late.
      </p>
      <div class="hero-actions">
        <a href="#contact" class="btn-primary">Get Involved</a>
        <a href="#mission" class="btn-ghost">Our Mission</a>
      </div>
    </div>
    <div class="pixel-shield" aria-hidden="true">
      <!-- 8×9 pixel grid forming a shield silhouette -->
      <div class="shield-grid" id="shieldGrid"></div>
      <div class="shield-label"><span>Pixel</span>Guard</div>
      <div class="shield-tagline">Foundation</div>
    </div>
  </div>
</section>

<!-- STATS -->
<section id="stats" aria-label="Key statistics">
  <div class="stats-inner">
    <div class="stat">
      <div class="stat-num">1 in 5</div>
      <div class="stat-label">children online receive unwanted sexual solicitation each year</div>
    </div>
    <div class="stat">
      <div class="stat-num">90%</div>
      <div class="stat-label">of child sexual exploitation occurs through gaming platforms and social media</div>
    </div>
    <div class="stat">
      <div class="stat-num">~40%</div>
      <div class="stat-label">of grooming victims know their perpetrator before meeting online</div>
    </div>
  </div>
</section>

<!-- MISSION PILLARS -->
<section id="mission">
  <div style="max-width:1100px;margin:0 auto;">
    <div class="section-eyebrow">What We Do</div>
    <h2 class="section-heading">Three pillars. One mission.</h2>
    <p class="section-sub">
      "Don't talk to strangers" isn't enough anymore. We teach families the real patterns of grooming, the platforms where it happens, and the tools to stop it.
    </p>
    <div class="pillars">
      <div class="pillar-card">
        <div class="pillar-icon">📚</div>
        <div class="pillar-title">Education</div>
        <p class="pillar-desc">Age-appropriate materials for kids 5–12, parent workshops, and school curricula that replace outdated "stranger danger" messaging with how predators actually operate.</p>
      </div>
      <div class="pillar-card">
        <div class="pillar-icon">📢</div>
        <div class="pillar-title">Advocacy</div>
        <p class="pillar-desc">Pushing for safer online platforms, better reporting tools within gaming environments, and policy-level protections for minors in digital spaces.</p>
      </div>
      <div class="pillar-card">
        <div class="pillar-icon">🎮</div>
        <div class="pillar-title">Community</div>
        <p class="pillar-desc">Working directly with gaming communities to shift culture from the inside — empowering players, streamers, and community managers to become part of the solution.</p>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT / FOUNDER -->
<section id="about">
  <div class="about-inner">
    <div>
      <div class="section-eyebrow">About the Foundation</div>
      <h2 class="section-heading">Built by someone who knows the game.</h2>
      <p class="section-sub">PixelGuard Foundation was incorporated in Washington State to address a gap in online safety education — one that leaves children vulnerable precisely because it ignores where they actually spend time.</p>
      <div class="founder-quote">
        <p>"The danger isn't strangers. It's the 'friend' your child has known online for six months who has been grooming them the entire time."</p>
        <div class="founder-byline">— Felisha Elmer (Tiger), Founder</div>
      </div>
    </div>
    <div class="about-callouts">
      <div class="callout-box">
        <strong>WA</strong>
        <span>State incorporated nonprofit</span>
      </div>
      <div class="callout-box">
        <strong>EIN</strong>
        <span>Federal tax ID registered</span>
      </div>
      <div class="callout-box">
        <strong>K-12</strong>
        <span>Educational programming focus</span>
      </div>
      <div class="callout-box">
        <strong>Free</strong>
        <span>Resources for families & educators</span>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT BY AUDIENCE -->
<section id="contact">
  <div class="contact-inner">
    <div class="contact-header">
      <div class="section-eyebrow">Get Involved</div>
      <h2 class="section-heading">How can we help you?</h2>
      <p class="section-sub">Whether you're a parent with questions, an educator building curriculum, or a donor looking to make an impact — we'd love to hear from you.</p>
    </div>
    <div class="audience-grid">
      <a href="mailto:hello@pixelguard.org?subject=Parent%20Inquiry" class="audience-card">
        <div class="audience-icon">👨‍👩‍👧</div>
        <div class="audience-title">Parents & Guardians</div>
        <p class="audience-desc">Get resources, ask questions, or request a workshop for your school or community group.</p>
        <div class="audience-link">Contact us →</div>
      </a>
      <a href="mailto:hello@pixelguard.org?subject=Educator%20Inquiry" class="audience-card">
        <div class="audience-icon">🏫</div>
        <div class="audience-title">Educators & Schools</div>
        <p class="audience-desc">Access curriculum materials and bring PixelGuard programming into your classroom.</p>
        <div class="audience-link">Request resources →</div>
      </a>
      <a href="mailto:hello@pixelguard.org?subject=Donor%20or%20Grant%20Inquiry" class="audience-card">
        <div class="audience-icon">🤝</div>
        <div class="audience-title">Donors & Funders</div>
        <p class="audience-desc">Support evidence-based online safety education for underserved communities in Spokane and beyond.</p>
        <div class="audience-link">Partner with us →</div>
      </a>
    </div>
    <div class="contact-direct">
      <div class="contact-direct-text">
        <h3>Reach us directly</h3>
        <p>We respond to every message. hello@pixelguard.org</p>
      </div>
      <a href="mailto:hello@pixelguard.org" class="btn-primary">Send an Email</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand"><span>Pixel</span>Guard Foundation</div>
    <div class="footer-meta">
      Washington State Nonprofit · EIN 42-2442335 · Spokane, WA ·
      <a href="mailto:hello@pixelguard.org">hello@pixelguard.org</a>
    </div>
  </div>
</footer>

<script>
  // Build pixel shield grid (8 columns × 9 rows = 72 cells)
  // 1 = teal on, 2 = bright highlight, 0 = dark off, 3 = accent dim
  const pattern = [
    0,1,1,1,1,1,1,0,
    1,1,1,1,1,1,1,1,
    1,1,1,1,1,1,1,1,
    1,1,2,2,2,2,1,1,
    0,1,1,2,2,1,1,0,
    0,1,1,1,1,1,1,0,
    0,0,1,1,1,1,0,0,
    0,0,0,1,1,0,0,0,
    0,0,0,0,0,0,0,0,
  ];

  const grid = document.getElementById('shieldGrid');
  grid.style.gridTemplateRows = `repeat(9, 1fr)`;

  pattern.forEach((v, i) => {
    const px = document.createElement('div');
    px.className = 'px ' + ['off','on','hi','ac'][v];
    grid.appendChild(px);
  });

  // Subtle flicker animation on random teal pixels
  const onPixels = grid.querySelectorAll('.px.on, .px.hi');
  setInterval(() => {
    const px = onPixels[Math.floor(Math.random() * onPixels.length)];
    px.style.opacity = (0.5 + Math.random() * 0.5).toFixed(2);
    setTimeout(() => { px.style.opacity = '1'; }, 300);
  }, 800);
</script>

</body>
</html>
