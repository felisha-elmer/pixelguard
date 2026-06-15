<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PixelGuard Foundation | Coming Soon</title>
  <meta name="description" content="PixelGuard Foundation is a gaming safety nonprofit coming soon. We educate children, parents, and gaming communities about predator safety in gaming environments." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy: #0D1B2A;
      --teal: #00C9B1;
      --teal-light: #00E5CC;
      --white: #F7F9FC;
      --slate: #4A5568;
    }

    html, body {
      height: 100%;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--navy);
      color: var(--white);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      -webkit-font-smoothing: antialiased;
      position: relative;
      overflow: hidden;
    }

    /* Grid background */
    body::before {
      content: '';
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,201,177,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,201,177,0.04) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
    }

    /* Glow */
    body::after {
      content: '';
      position: absolute;
      top: -10%;
      left: 50%;
      transform: translateX(-50%);
      width: 700px;
      height: 700px;
      background: radial-gradient(circle, rgba(0,201,177,0.1) 0%, transparent 65%);
      pointer-events: none;
    }

    .container {
      position: relative;
      z-index: 1;
      max-width: 560px;
      width: 100%;
      text-align: center;
    }

    /* Pixel shield */
    .shield-grid {
      display: grid;
      grid-template-columns: repeat(8, 1fr);
      grid-template-rows: repeat(9, 1fr);
      gap: 4px;
      width: 100px;
      height: 110px;
      margin: 0 auto 1.75rem;
    }

    .px { border-radius: 2px; }
    .px.on { background: var(--teal); }
    .px.hi { background: #00ffe8; }
    .px.off { background: rgba(255,255,255,0.05); }

    .wordmark {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1rem;
      font-weight: 700;
      color: var(--white);
      letter-spacing: -0.01em;
      margin-bottom: 3rem;
    }

    .wordmark span { color: var(--teal); }

    h1 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(2rem, 5vw, 3rem);
      font-weight: 700;
      letter-spacing: -0.03em;
      line-height: 1.1;
      margin-bottom: 1.25rem;
    }

    h1 em {
      font-style: normal;
      color: var(--teal);
    }

    .mission {
      color: rgba(247,249,252,0.6);
      font-size: 1rem;
      line-height: 1.7;
      margin-bottom: 2.5rem;
    }

    /* Email form */
    .signup-form {
      display: flex;
      gap: 0.625rem;
      margin-bottom: 1rem;
      flex-wrap: wrap;
      justify-content: center;
    }

    .signup-form input {
      flex: 1;
      min-width: 220px;
      padding: 0.8125rem 1.1rem;
      border-radius: 8px;
      border: 1px solid rgba(0,201,177,0.3);
      background: rgba(255,255,255,0.05);
      color: var(--white);
      font-family: 'Inter', sans-serif;
      font-size: 0.9375rem;
      outline: none;
      transition: border-color 0.2s;
    }

    .signup-form input::placeholder { color: rgba(247,249,252,0.35); }
    .signup-form input:focus { border-color: var(--teal); }

    .signup-form button {
      padding: 0.8125rem 1.5rem;
      background: var(--teal);
      color: var(--navy);
      border: none;
      border-radius: 8px;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 0.9375rem;
      cursor: pointer;
      transition: background 0.2s, transform 0.15s;
      white-space: nowrap;
    }

    .signup-form button:hover {
      background: var(--teal-light);
      transform: translateY(-1px);
    }

    .form-note {
      font-size: 0.8rem;
      color: rgba(247,249,252,0.3);
      margin-bottom: 2.5rem;
    }

    .divider {
      width: 40px;
      height: 1px;
      background: rgba(0,201,177,0.3);
      margin: 0 auto 2.5rem;
    }

    .contact-line {
      font-size: 0.875rem;
      color: rgba(247,249,252,0.45);
    }

    .contact-line a {
      color: var(--teal);
      text-decoration: none;
      font-weight: 600;
    }

    .contact-line a:hover { color: var(--teal-light); }

    .footer-note {
      margin-top: 3rem;
      font-size: 0.75rem;
      color: rgba(247,249,252,0.2);
    }

    /* Success state */
    .success-msg {
      display: none;
      color: var(--teal);
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 2.5rem;
    }

    @media (prefers-reduced-motion: reduce) {
      * { transition: none !important; animation: none !important; }
    }
  </style>
</head>
<body>
  <div class="container">

    <!-- Logo -->
    <div class="shield-grid" id="shieldGrid" aria-hidden="true"></div>
    <div class="wordmark"><span>Pixel</span>Guard Foundation</div>

    <!-- Headline -->
    <h1>Something <em>important</em><br>is loading.</h1>
    <p class="mission">
      We're building a gaming safety nonprofit dedicated to protecting children from predators in gaming environments. Our educational programming, resources, and community tools are on their way.
    </p>

    <!-- Email signup -->
    <div class="signup-form">
      <input type="email" id="emailInput" placeholder="your@email.com" aria-label="Email address" />
      <button onclick="handleSignup()">Notify Me</button>
    </div>
    <p class="form-note">We'll let you know when we launch. No spam, ever.</p>
    <p class="success-msg" id="successMsg">✓ You're on the list — we'll be in touch!</p>

    <div class="divider"></div>

    <!-- Contact -->
    <p class="contact-line">
      Questions or partnerships: <a href="mailto:hello@pixelguard.org">hello@pixelguard.org</a>
    </p>

    <p class="footer-note">Washington State Nonprofit · EIN 42-2442335 · Spokane, WA</p>

  </div>

  <script>
    // Build pixel shield
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
    pattern.forEach(v => {
      const px = document.createElement('div');
      px.className = 'px ' + ['off','on','hi'][v];
      grid.appendChild(px);
    });

    // Flicker
    const onPx = grid.querySelectorAll('.px.on, .px.hi');
    setInterval(() => {
      const px = onPx[Math.floor(Math.random() * onPx.length)];
      px.style.opacity = (0.4 + Math.random() * 0.6).toFixed(2);
      setTimeout(() => px.style.opacity = '1', 300);
    }, 900);

    // Email signup (mailto fallback — no backend needed)
    function handleSignup() {
      const email = document.getElementById('emailInput').value.trim();
      if (!email || !email.includes('@')) {
        document.getElementById('emailInput').focus();
        return;
      }
      // Open mailto so signup lands in your inbox
      window.location.href = `mailto:hello@pixelguard.org?subject=Launch%20Notification%20Signup&body=Please%20add%20me%20to%20the%20launch%20list%3A%20${encodeURIComponent(email)}`;
      document.getElementById('emailInput').value = '';
      document.querySelector('.signup-form').style.display = 'none';
      document.querySelector('.form-note').style.display = 'none';
      document.getElementById('successMsg').style.display = 'block';
    }

    document.getElementById('emailInput').addEventListener('keydown', e => {
      if (e.key === 'Enter') handleSignup();
    });
  </script>
</body>
</html>
