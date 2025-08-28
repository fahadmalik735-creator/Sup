# Sup
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Happy Birthday! 🎂🎈</title>
  <style>
    :root {
      --bg1: #0f1020;
      --bg2: #1b1e3b;
      --accent: #ff6ec7;
      --accent2: #ffd166;
      --accent3: #7bdff2;
      --text: #ffffff;
      --muted: #e0e0e0;
    }

    * { box-sizing: border-box; }

    html, body {
      height: 100%;
      margin: 0;
      font-family: ui-rounded, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
      color: var(--text);
      background: radial-gradient(1200px 800px at 70% -10%, #25114255, transparent 60%),
                  radial-gradient(900px 600px at 10% 10%, #1e3a8a33, transparent 55%),
                  linear-gradient(160deg, var(--bg1), var(--bg2));
      overflow-x: hidden;
    }

    /* Floating balloons */
    .balloon {
      position: absolute;
      width: 70px; height: 90px;
      border-radius: 50% 50% 45% 45% / 55% 55% 45% 45%;
      opacity: 0.85;
      filter: drop-shadow(0 12px 18px rgba(0,0,0,0.25));
      animation: float 12s ease-in-out infinite;
    }
    .balloon::after {
      content: "";
      position: absolute;
      left: 50%; bottom: -40px;
      width: 2px; height: 44px;
      background: #ffffff99;
      transform: translateX(-50%);
    }
    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-40px) rotate(2deg); }
    }

    /* Bunting garland */
    .bunting {
      position: absolute; inset: 0 auto auto 0;
      width: 100%; height: 140px; pointer-events: none;
      opacity: 0.55;
    }

    /* Center card */
    .card {
      max-width: 980px;
      margin: 8vh auto 6vh;
      margin-top: 8%;
      padding: 32px;
      background: linear-gradient(180deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
      border: 1px solid rgba(255,255,255,0.14);
      border-radius: 24px;
      backdrop-filter: blur(6px);
      box-shadow: 0 24px 60px rgba(0,0,0,0.35);
    }

    .title {
      font-size: clamp(32px, 6vw, 76px);
      line-height: 1.05;
      text-align: center;
      margin: 8px 0 16px;
      letter-spacing: 0.5px;
    }
    .gradient-text {
      background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .subtitle {
      text-align: center; margin: 0 0 20px; font-size: clamp(16px, 2.5vw, 22px); color: var(--muted);
    }

    /* Cake + candles */
    .stage {
      display: grid; place-items: center; margin: 24px 0;
    }
    .cake {
      width: min(520px, 90vw);
    }
    .flame { transform-origin: center; animation: flicker 1.2s ease-in-out infinite; }
    .flame:nth-child(2) { animation-delay: 0.25s; }
    .flame:nth-child(3) { animation-delay: 0.5s; }
    @keyframes flicker {
      0%, 100% { transform: translateY(0) scale(1); filter: drop-shadow(0 0 6px #ffd166); }
      50% { transform: translateY(-1px) scale(1.06); filter: drop-shadow(0 0 10px #ffd166); }
    }

    /* Buttons */
    .actions { display: flex; justify-content: center; flex-wrap: wrap; gap: 12px; margin-top: 8px; }
    .btn {
      appearance: none; border: 0; cursor: pointer;
      padding: 12px 18px; border-radius: 999px;
      background: linear-gradient(90deg, #ffffff, #e7e7e7);
      color: #111; font-weight: 700; letter-spacing: 0.3px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.25), inset 0 -2px 0 rgba(0,0,0,0.08);
      transition: transform 0.12s ease, box-shadow 0.2s ease;
    }
    .btn:hover { transform: translateY(-2px); box-shadow: 0 12px 26px rgba(0,0,0,0.3), inset 0 -2px 0 rgba(0,0,0,0.08); }
    .btn:active { transform: translateY(0); }

    /* Footer note */
    footer { text-align: center; color: #d1d5db; font-size: 14px; margin: 26px 0 6px; opacity: 0.9; }

    /* Confetti canvas */
    #confetti { position: fixed; inset: 0; pointer-events: none; }

    /* Responsive finesse */
    .row { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; align-items: center; }
    @media (max-width: 820px) { .row { grid-template-columns: 1fr; } }
  </style>
</head>
<body>
  <!-- Decorative bunting at the top -->
  <svg class="bunting" viewBox="0 0 1200 160" preserveAspectRatio="none" aria-hidden="true">
    <defs>
      <linearGradient id="g1" x1="0" y1="0" x2="1" y2="1">
        <stop offset="0%" stop-color="#ff6ec7"/>
        <stop offset="100%" stop-color="#7bdff2"/>
      </linearGradient>
      <linearGradient id="g2" x1="0" y1="0" x2="1" y2="1">
        <stop offset="0%" stop-color="#ffd166"/>
        <stop offset="100%" stop-color="#caffbf"/>
      </linearGradient>
    </defs>
    <path d="M0,30 C200,120 400,-40 600,50 C800,140 1000,0 1200,70" fill="none" stroke="url(#g1)" stroke-width="6"/>
    <path d="M0,70 C180,140 420,10 600,90 C780,170 1000,30 1200,110" fill="none" stroke="url(#g2)" stroke-width="6"/>
    <!-- pennants -->
    <g>
      <!-- generated triangles -->
      <polygon points="70,52 110,52 90,100" fill="#ff6ec7"/>
      <polygon points="170,80 210,80 190,128" fill="#7bdff2"/>
      <polygon points="270,42 310,42 290,90" fill="#ffd166"/>
      <polygon points="370,68 410,68 390,116" fill="#caffbf"/>
      <polygon points="470,36 510,36 490,84" fill="#b28dff"/>
      <polygon points="570,86 610,86 590,134" fill="#ffadad"/>
      <polygon points="670,48 710,48 690,96" fill="#fdffb6"/>
      <polygon points="770,76 810,76 790,124" fill="#a0c4ff"/>
      <polygon points="870,40 910,40 890,88" fill="#9bf6ff"/>
      <polygon points="970,72 1010,72 990,120" fill="#ffd6a5"/>
      <polygon points="1070,46 1110,46 1090,94" fill="#bdb2ff"/>
    </g>
  </svg>

  <!-- Floating balloons (positions randomized by JS) -->
  <div id="balloons"></div>

  <canvas id="confetti"></canvas>

  <main class="card">
    <h1 class="title gradient-text">Happy Birthday, Sister Maham Sajid!</h1>
    <p class="subtitle">Wishing you joy, health, and all your favorite things — today and always.</p>

    <div class="stage">
      <!-- Cute cake SVG -->
      <svg class="cake" viewBox="0 0 600 360" xmlns="http://www.w3.org/2000/svg" aria-label="Birthday cake with candles">
        <!-- cake base -->
        <rect x="120" y="190" width="360" height="110" rx="18" fill="#7c3aed" opacity="0.18"/>
        <rect x="120" y="170" width="360" height="110" rx="18" fill="#f1a7ff"/>
        <!-- frosting drip -->
        <path d="M120,170 h360  
            v30 
            c-20,20 -40,-10 -60,10 
            c-20,20 -40,-10 -60,10 
            c-20,20 -40,-10 -60,10 
            c-20,20 -40,-10 -60,10 
            c-20,20 -40,-10 -60,10 
            c-20,20 -40,-10 -60,10 
            v-80z"
        fill="#fff" opacity="0.95"/>
        <!-- candles -->
        <g>
          <rect x="220" y="110" width="16" height="60" rx="4" fill="#ff8fab"/>
          <rect x="260" y="110" width="16" height="60" rx="4" fill="#a0c4ff"/>
          <rect x="300" y="110" width="16" height="60" rx="4" fill="#ffd6a5"/>
          <rect x="340" y="110" width="16" height="60" rx="4" fill="#caffbf"/>
          <rect x="380" y="110" width="16" height="60" rx="4" fill="#bdb2ff"/>
        </g>
        <!-- flames -->
        <g>
          <ellipse class="flame" cx="228" cy="102" rx="8" ry="12" fill="#ffd166"/>
          <ellipse class="flame" cx="268" cy="102" rx="8" ry="12" fill="#ffd166"/>
          <ellipse class="flame" cx="308" cy="102" rx="8" ry="12" fill="#ffd166"/>
          <ellipse class="flame" cx="348" cy="102" rx="8" ry="12" fill="#ffd166"/>
          <ellipse class="flame" cx="388" cy="102" rx="8" ry="12" fill="#ffd166"/>
        </g>
      </svg>
    </div>

    
        <div class="actions">
          <button class="btn" id="confettiBtn">Launch Confetti</button>
          <button class="btn" id="toggleBalloons">Toggle Balloons</button>
        </div>
  </main>

  <script>
    // ======== Balloons ========
    const balloonWrap = document.getElementById('balloons');
    const colors = ['#ff6ec7', '#7bdff2', '#ffd166', '#caffbf', '#b28dff', '#ffadad', '#fdffb6', '#a0c4ff'];

    function rand(min, max) { return Math.random() * (max - min) + min; }

    function createBalloons(count = 10) {
      balloonWrap.innerHTML = '';
      for (let i = 0; i < count; i++) {
        const b = document.createElement('div');
        b.className = 'balloon';
        b.style.left = rand(2, 92) + 'vw';
        b.style.top = rand(55, 88) + 'vh';
        b.style.background = colors[i % colors.length];
        b.style.transform = `scale(${rand(0.7, 1.2)})`;
        b.style.animationDelay = rand(0, 6) + 's';
        balloonWrap.appendChild(b);
      }
    }
    createBalloons(14);

    const toggleBalloonsBtn = document.getElementById('toggleBalloons');
    let balloonsVisible = true;
    toggleBalloonsBtn.addEventListener('click', () => {
      balloonsVisible = !balloonsVisible;
      balloonWrap.style.display = balloonsVisible ? 'block' : 'none';
    });

    // ======== Confetti ========
    const canvas = document.getElementById('confetti');
    const ctx = canvas.getContext('2d');
    let particles = [];

    function resize() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resize);
    resize();

    class Particle {
      constructor(x, y) {
        this.x = x; this.y = y;
        this.w = rand(6, 12); this.h = rand(8, 14);
        this.vx = rand(-3, 3); this.vy = rand(-9, -5);
        this.rotate = rand(0, Math.PI * 2);
        this.vr = rand(-0.2, 0.2);
        this.color = colors[Math.floor(rand(0, colors.length))];
        this.shape = Math.random() < 0.65 ? 'rect' : 'circle';
        this.life = 0; this.maxLife = rand(120, 200);
      }
      step() {
        this.life++;
        this.vy += 0.15; // gravity
        this.x += this.vx;
        this.y += this.vy;
        this.rotate += this.vr;
        if (this.y > canvas.height + 20 || this.life > this.maxLife) this.dead = true;
      }
      draw() {
        ctx.save();
        ctx.translate(this.x, this.y);
        ctx.rotate(this.rotate);
        ctx.fillStyle = this.color;
        if (this.shape === 'rect') {
          ctx.fillRect(-this.w/2, -this.h/2, this.w, this.h);
        } else {
          ctx.beginPath();
          ctx.arc(0, 0, this.w/2, 0, Math.PI * 2);
          ctx.fill();
        }
        ctx.restore();
      }
    }

    function burst(x, y, n = 180) {
      for (let i = 0; i < n; i++) particles.push(new Particle(x, y));
    }

    function loop() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      particles = particles.filter(p => !p.dead);
      for (const p of particles) { p.step(); p.draw(); }
      requestAnimationFrame(loop);
    }
    loop();

    // Launch on load and on button
    function centerBurst() { burst(canvas.width / 2, canvas.height * 0.25, 240); }
    window.addEventListener('load', centerBurst);

    document.getElementById('confettiBtn').addEventListener('click', () => {
      burst(rand(canvas.width * 0.2, canvas.width * 0.8), rand(canvas.height * 0.1, canvas.height * 0.4), 240);
    });

    // Also trigger confetti on any click/tap
    window.addEventListener('pointerdown', (e) => burst(e.clientX, e.clientY, 180));
  </script>
</body>
</html>
