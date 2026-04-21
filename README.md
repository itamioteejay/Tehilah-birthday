
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>For My Empress 👑</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Quicksand:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { 
      margin: 0; 
      padding: 0; 
      box-sizing: border-box; 
    }

    :root {
      --gold: #c9a84c; 
      --gold2: #f0d080; 
      --soft: #e8dcc8;
      --dim: #9a8f7a; 
      --dark: #050810; 
      --mid: #0b0f1e;
      --font-d: 'Cormorant Garamond', serif;
      --font-b: 'Quicksand', sans-serif;
    }

    html {
      scroll-behavior: smooth;
      scroll-snap-type: y mandatory;
    }

    body {
      background: var(--dark); 
      color: var(--soft);
      font-family: var(--font-b); 
      font-weight: 300;
      overflow-x: hidden;
    }

    ::-webkit-scrollbar { width: 3px; }
    ::-webkit-scrollbar-thumb { background: var(--gold); }

    .no-scroll { overflow: hidden; }

    #entry-loader {
      position: fixed; 
      inset: 0; 
      background: var(--dark);
      z-index: 9999; 
      display: flex; 
      align-items: center; 
      justify-content: center;
      transition: opacity 1.5s, visibility 1.5s;
    }

    #entry-loader.hidden { 
      opacity: 0; 
      visibility: hidden; 
    }

    .loader-text {
      font-family: var(--font-d);
      font-size: clamp(1.5rem, 5vw, 2.5rem);
      font-style: italic; 
      color: var(--gold2);
      letter-spacing: .1em; 
      opacity: 0;
      animation: fadeInOut 2.5s ease-in-out forwards;
    }

    @keyframes fadeInOut {
      0% { opacity: 0; } 
      30% { opacity: 1; } 
      70% { opacity: 1; } 
      100% { opacity: 0; }
    }

    section {
      min-height: 100vh; 
      display: flex; 
      flex-direction: column;
      align-items: center; 
      justify-content: center;
      padding: 60px 24px 90px; 
      position: relative; 
      overflow: hidden;
      scroll-snap-align: start;
      scroll-snap-stop: always;
    }

    #s0 { background: radial-gradient(ellipse at 50% 55%, #0d1535, var(--dark)); }
    #s1, #s3, #s5, #s7 { background: #07090f; }
    #s2, #s4, #s6 { background: linear-gradient(160deg, #09101f, #0d1530); }
    #s8 { background: linear-gradient(180deg, #090f1d, var(--dark)); }

    .box {
      max-width: 680px;
      width: 100%;
      text-align: center;
      z-index: 2;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 28px;
    }

    .emp-img {
      width: 100%;
      max-width: 260px;
      aspect-ratio: 4/5;
      object-fit: cover;
      border-radius: 12px;
      border: 1px solid var(--dim);
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
    }

    /* ── TYPEWRITER: types once, then stays with a static cursor ── */
    .typed-text {
      font-family: var(--font-d);
      font-size: clamp(1.45rem, 4.5vw, 2.1rem);
      line-height: 1.65;
      font-style: italic;
      color: var(--soft);
      display: block;
      width: 100%;
      white-space: pre-wrap;
      word-break: break-word;
      overflow: hidden;
      min-height: 2em;
    }

    /* Blinking cursor appended via JS */
    .cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: var(--gold2);
      margin-left: 3px;
      vertical-align: middle;
      animation: blink 1s step-start infinite;
    }

    .cursor.done {
      /* Keep cursor visible but stop blinking once fully typed */
      animation: none;
      opacity: 0;
    }

    @keyframes blink {
      50% { opacity: 0; }
    }

    /* ── PREMIUM NEXT BUTTON ── */
    .next-btn {
      position: relative;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-family: var(--font-b);
      font-size: 1rem;
      font-weight: 500;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--dark);
      background: linear-gradient(135deg, #f0d080 0%, #c9a84c 50%, #f0d080 100%);
      background-size: 200% 200%;
      background-position: 0% 50%;
      padding: 14px 40px;
      border-radius: 50px;
      border: none;
      cursor: pointer;
      box-shadow:
        0 0 0 1px rgba(201,168,76,0.3),
        0 4px 16px rgba(201,168,76,0.25),
        0 12px 40px rgba(0,0,0,0.5),
        inset 0 1px 0 rgba(255,255,255,0.25);
      transition: 
        background-position 0.5s ease,
        box-shadow 0.3s ease,
        transform 0.2s ease,
        letter-spacing 0.3s ease;
      overflow: hidden;
    }

    .next-btn::before {
      content: '';
      position: absolute;
      inset: 0;
      border-radius: 50px;
      background: linear-gradient(135deg, transparent 30%, rgba(255,255,255,0.18) 50%, transparent 70%);
      background-size: 200% 200%;
      background-position: -100% 0;
      transition: background-position 0.55s ease;
    }

    .next-btn:hover {
      background-position: 100% 50%;
      box-shadow:
        0 0 0 1px rgba(240,208,128,0.5),
        0 6px 24px rgba(201,168,76,0.45),
        0 18px 50px rgba(0,0,0,0.55),
        inset 0 1px 0 rgba(255,255,255,0.35);
      transform: translateY(-2px) scale(1.02);
      letter-spacing: 0.22em;
    }

    .next-btn:hover::before {
      background-position: 200% 0;
    }

    .next-btn:active {
      transform: translateY(0px) scale(0.98);
      box-shadow:
        0 0 0 1px rgba(201,168,76,0.4),
        0 2px 8px rgba(201,168,76,0.3),
        0 6px 20px rgba(0,0,0,0.5),
        inset 0 1px 0 rgba(255,255,255,0.2);
    }

    /* Arrow icon inside button */
    .next-btn .btn-arrow {
      display: inline-block;
      font-size: 1.1em;
      transition: transform 0.3s ease;
    }

    .next-btn:hover .btn-arrow {
      transform: translateX(4px);
    }

    .footer {
      font-family: var(--font-d);
      color: var(--gold2);
      font-size: 1.4rem;
      font-style: italic;
      margin-top: 10px;
    }
  </style>
</head>
<body class="no-scroll">

<div id="entry-loader">
  <div class="loader-text">A universe built for you...</div>
</div>

<section id="s0">
  <div class="box">
    <img src="image1.jpg" alt="Image 1" class="emp-img">
    <p class="typed-text" data-text="In a universe this vast… I still found you"></p>
    <a href="#s1" class="next-btn">Start <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s1">
  <div class="box">
    <img src="image2.jpg" alt="Image 2" class="emp-img">
    <p class="typed-text" data-text="Before you… things were just normal, nothing really stood out like that…"></p>
    <a href="#s2" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s2">
  <div class="box">
    <img src="image3.jpg" alt="Image 3" class="emp-img">
    <p class="typed-text" data-text="A beautiful tall girl… with that model-like posture, the way you carry yourself — so effortless. You don't even try, but somehow you still stand out every single time."></p>
    <a href="#s3" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s3">
  <div class="box">
    <img src="image4.jpg" alt="Image 4" class="emp-img">
    <p class="typed-text" data-text="I love the way you talk. You're so good with your words, like… you just know how to express yourself, and your voice… It's soft, melodious, like God really took His time with you, sometimes it actually feels like He sent an angel down… and gave her that voice."></p>
    <a href="#s4" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s4">
  <div class="box">
    <img src="image5.jpg" alt="Image 5" class="emp-img">
    <p class="typed-text" data-text="You're the first person in a very long time that made me feel like this, and I don't take that lightly at all. You make me happy, in ways I didn't expect."></p>
    <a href="#s5" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s5">
  <div class="box">
    <img src="image6.jpg" alt="Image 6" class="emp-img">
    <p class="typed-text" data-text="My lovely, beautiful, everlasting empress… You really are different. Everything about you just feels… special. And yeah, your ever glowing forehead 😭, it's actually elite!"></p>
    <a href="#s6" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s6">
  <div class="box">
    <img src="image7.jpg" alt="Image 7" class="emp-img">
    <p class="typed-text" data-text="All those late-night talks… the random conversations, the quiet moments. Even when we don't always see things the same way, what matters is — I genuinely care about you."></p>
    <a href="#s7" class="next-btn">Next <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s7">
  <div class="box">
    <img src="image8.jpg" alt="Image 8" class="emp-img">
    <p class="typed-text" data-text="Today is yours. I just want to see you win in everything. I pray God elevates you, gives you more wisdom, knowledge, patience, happiness, money, blessings, and more of everything you deserve. May all your heart's desires be fulfilled."></p>
    <a href="#s8" class="next-btn">Final <span class="btn-arrow">→</span></a>
  </div>
</section>

<section id="s8">
  <div class="box">
    <img src="image9.jpg" alt="Image 9" class="emp-img">
    <p class="typed-text" data-text="I'm always rooting for you, always in your corner. Your biggest fan… no matter what. And honestly, it's you, every time. My empress ❤️ I love you… all of you."></p>
    <p class="footer">With lots of love ❤ TeeJay</p>
  </div>
</section>

<script>
  /* ── Entry loader ── */
  window.addEventListener('load', () => {
    setTimeout(() => {
      document.getElementById('entry-loader').classList.add('hidden');
      document.body.classList.remove('no-scroll');
    }, 2000);
  });

  /* ── Typewriter: types once, stays on screen ── */
  const SPEED = 38; // ms per character — tweak freely

  function typeOnce(el) {
    const text = el.getAttribute('data-text') || '';
    if (el.dataset.typed) return; // already typed
    el.dataset.typed = '1';
    el.textContent = '';

    // Create cursor span
    const cursor = document.createElement('span');
    cursor.className = 'cursor';
    el.appendChild(cursor);

    let i = 0;
    function tick() {
      if (i < text.length) {
        // Insert character just before the cursor
        el.insertBefore(document.createTextNode(text[i]), cursor);
        i++;
        setTimeout(tick, SPEED);
      } else {
        // Done — hide cursor
        cursor.classList.add('done');
      }
    }
    tick();
  }

  /* ── IntersectionObserver: fire typewriter when section scrolls into view ── */
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const el = entry.target.querySelector('.typed-text');
        if (el) {
          // Small delay so the section is fully settled before typing starts
          setTimeout(() => typeOnce(el), 300);
        }
      }
    });
  }, { threshold: 0.5 });

  document.querySelectorAll('section').forEach(sec => observer.observe(sec));
</script>
</body>
</html>
