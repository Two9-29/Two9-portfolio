<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TWO9 — Portfolio</title>

  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Space+Grotesk:wght@500;600;700&display=swap" rel="stylesheet">

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Space Grotesk', 'sans-serif'],
          },
          colors: {
            dark: '#09090b',
            card: '#111113',
            accent: '#a3e635',
          }
        }
      }
    }
  </script>

  <style>
    html { scroll-behavior: smooth; }
    body { background: #09090b; overflow-x: hidden; }

    .nav-blur {
      backdrop-filter: blur(12px);
      background: rgba(9, 9, 11, 0.85);
    }

    /* ===== STACKED CARDS ===== */
    .stack-container {
      position: relative;
      height: 400vh;
    }

    .stack-sticky {
      position: sticky;
      top: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .stack-cards {
      position: relative;
      width: 100%;
      max-width: 42rem;
      height: 28rem;
    }

    .stack-card {
      position: absolute;
      inset: 0;
      background: #111113;
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 1.5rem;
      padding: 1.75rem;
      display: flex;
      flex-direction: column;
      cursor: pointer;
      transition: border-color 0.3s, box-shadow 0.3s;
      will-change: transform, opacity;
      -webkit-tap-highlight-color: transparent;
    }

    /* RGB Glow */
    .stack-card.rgb-active {
      border: 2px solid transparent;
      background: 
        linear-gradient(#111113, #111113) padding-box,
        linear-gradient(var(--rgb-angle, 0deg), #ff006e, #8338ec, #3a86ff, #06d6a0, #ffbe0b, #ff006e) border-box;
      box-shadow: 
        0 0 25px rgba(255, 0, 110, 0.5),
        0 0 50px rgba(131, 56, 236, 0.35),
        0 0 80px rgba(58, 134, 255, 0.25);
      animation: rgbRotate 3s linear infinite;
    }

    @keyframes rgbRotate {
      to { --rgb-angle: 360deg; }
    }

    @property --rgb-angle {
      syntax: "<angle>";
      initial-value: 0deg;
      inherits: false;
    }

    @media (min-width: 640px) {
      .stack-cards { height: 32rem; }
      .stack-card { padding: 2rem; }
    }

    /* ===== TV SCREEN ===== */
    .tv-wrapper {
      opacity: 0;
      transform: translateY(120px) scale(0.9);
      transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
    }

    .tv-wrapper.visible {
      opacity: 1;
      transform: translateY(0) scale(1);
    }

    .tv-frame {
      background: linear-gradient(145deg, #1a1a1e, #0d0d0f);
      border-radius: 1.25rem;
      padding: 14px;
      box-shadow: 
        0 30px 60px -15px rgba(0,0,0,0.8),
        inset 0 1px 1px rgba(255,255,255,0.05);
    }

    .tv-screen {
      background: #050505;
      border-radius: 0.8rem;
      overflow: hidden;
      aspect-ratio: 16 / 9;
      position: relative;
      box-shadow: inset 0 0 30px rgba(0,0,0,0.8);
    }

    /* subtle screen glow */
    .tv-screen::after {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at center, rgba(163,230,53,0.03) 0%, transparent 70%);
      pointer-events: none;
    }

    .tv-stand {
      width: 38%;
      height: 12px;
      background: linear-gradient(to bottom, #222, #111);
      margin: 0 auto;
      border-radius: 0 0 6px 6px;
      position: relative;
    }

    .tv-stand::after {
      content: '';
      position: absolute;
      bottom: -7px;
      left: 50%;
      transform: translateX(-50%);
      width: 65%;
      height: 7px;
      background: #0a0a0a;
      border-radius: 4px;
    }
  </style>
</head>
<body class="font-sans text-zinc-300 antialiased">

  <!-- Navbar -->
  <nav class="fixed top-0 w-full z-50 nav-blur border-b border-white/5">
    <div class="max-w-5xl mx-auto px-5 h-16 flex items-center justify-between">
      <a href="#" class="font-display font-bold text-xl text-white">TWO9</a>
      <div class="hidden sm:flex gap-8 text-sm">
        <a href="#work" class="hover:text-accent transition">Work</a>
        <a href="#about" class="hover:text-accent transition">About</a>
        <a href="#contact" class="hover:text-accent transition">Contact</a>
      </div>
      <button id="menuBtn" class="sm:hidden text-white p-2">
        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
      </button>
    </div>
    <div id="mobileMenu" class="hidden sm:hidden border-t border-white/5 bg-dark">
      <div class="flex flex-col px-5 py-4 gap-4 text-sm">
        <a href="#work">Work</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
  </nav>

  <!-- Hero -->
  <section class="min-h-screen flex items-center pt-20">
    <div class="max-w-5xl mx-auto px-5 w-full">
      <p class="text-accent font-medium mb-3 text-sm">Hey, I’m</p>
      <h1 class="font-display text-5xl sm:text-7xl font-bold text-white mb-6">TWO9</h1>
      <p class="text-lg sm:text-2xl text-zinc-400 max-w-xl leading-relaxed mb-10">
        Building clean digital experiences.<br class="hidden sm:block">
        Developer • Designer • Creator
      </p>
      <div class="flex flex-wrap gap-4">
        <a href="#work" class="px-7 py-3.5 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition">View Work</a>
        <a href="#contact" class="px-7 py-3.5 border border-white/20 rounded-full hover:border-accent hover:text-accent transition">Get in touch</a>
      </div>
    </div>
  </section>

  <!-- STACKED WORK -->
  <section id="work">
    <div class="max-w-5xl mx-auto px-5 pt-20 pb-8">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-3">Selected Work</h2>
      <p class="text-zinc-500 text-sm">Scroll to stack • Tap a card for RGB glow</p>
    </div>

    <div class="stack-container" id="stackContainer">
      <div class="stack-sticky">
        <div class="stack-cards" id="stackCards">

          <div class="stack-card" data-index="0">
            <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">Project Image 01</div>
            <h3 class="text-2xl font-semibold text-white mb-2">Project One</h3>
            <p class="text-zinc-400 text-sm mb-5 flex-1">A clean and modern web application focused on performance and beautiful interactions.</p>
            <div class="flex flex-wrap gap-2 text-xs">
              <span class="px-2.5 py-1 bg-white/5 rounded-full">React</span>
              <span class="px-2.5 py-1 bg
