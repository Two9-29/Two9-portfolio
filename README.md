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
    .stack-section {
      position: relative;
    }

    .stack-container {
      position: relative;
      height: 400vh; /* controls how long the stacking lasts */
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
      transition: none; /* we control everything with JS */
      will-change: transform, opacity;
    }

    @media (min-width: 640px) {
      .stack-cards { height: 32rem; }
      .stack-card { padding: 2rem; }
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

  <!-- ==================== STACKED WORK SECTION ==================== -->
  <section id="work" class="stack-section">
    <div class="max-w-5xl mx-auto px-5 pt-20 pb-10">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-6">Selected Work</h2>
      <p class="text-zinc-500 mb-10">Scroll down to explore the projects</p>
    </div>

    <div class="stack-container" id="stackContainer">
      <div class="stack-sticky">
        <div class="stack-cards" id="stackCards">

          <!-- Card 1 -->
          <div class="stack-card" data-index="0">
            <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
              Project Image 01
            </div>
            <h3 class="text-2xl font-semibold text-white mb-2">Project One</h3>
            <p class="text-zinc-400 text-sm mb-5 flex-1">A clean and modern web application focused on performance and beautiful interactions.</p>
            <div class="flex flex-wrap gap-2 text-xs">
              <span class="px-2.5 py-1 bg-white/5 rounded-full">React</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Tailwind</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Next.js</span>
            </div>
          </div>

          <!-- Card 2 -->
          <div class="stack-card" data-index="1">
            <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
              Project Image 02
            </div>
            <h3 class="text-2xl font-semibold text-white mb-2">Project Two</h3>
            <p class="text-zinc-400 text-sm mb-5 flex-1">Full-stack platform with real-time features and a refined user experience.</p>
            <div class="flex flex-wrap gap-2 text-xs">
              <span class="px-2.5 py-1 bg-white/5 rounded-full">TypeScript</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Node</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Postgres</span>
            </div>
          </div>

          <!-- Card 3 -->
          <div class="stack-card" data-index="2">
            <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
              Project Image 03
            </div>
            <h3 class="text-2xl font-semibold text-white mb-2">Project Three</h3>
            <p class="text-zinc-400 text-sm mb-5 flex-1">Experimental interface exploring motion, 3D and creative coding.</p>
            <div class="flex flex-wrap gap-2 text-xs">
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Three.js</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Framer Motion</span>
            </div>
          </div>

          <!-- Card 4 -->
          <div class="stack-card" data-index="3">
            <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
              Project Image 04
            </div>
            <h3 class="text-2xl font-semibold text-white mb-2">Project Four</h3>
            <p class="text-zinc-400 text-sm mb-5 flex-1">AI-powered tool that turns ideas into production-ready interfaces.</p>
            <div class="flex flex-wrap gap-2 text-xs">
              <span class="px-2.5 py-1 bg-white/5 rounded-full">Python</span>
              <span class="px-2.5 py-1 bg-white/5 rounded-full">AI</span>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>

  <!-- About -->
  <section id="about" class="py-24 sm:py-32 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-5">
      <div class="grid md:grid-cols-5 gap-12 items-start">
        <div class="md:col-span-2">
          <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-8">About</h2>
          <div class="w-24 h-24 rounded-2xl bg-gradient-to-br from-accent/20 to-emerald-900/20 border border-accent/20 flex items-center justify-center text-2xl font-display font-bold text-accent">
            T9
          </div>
        </div>
        <div class="md:col-span-3 space-y-5 text-lg text-zinc-400 leading-relaxed">
          <p>I’m TWO9 — a developer who cares about clean code, sharp design, and products that feel good to use.</p>
          <p>I work across the stack but love the frontend the most: fast interfaces, smooth interactions, and thoughtful details.</p>
          <p>Currently open to new opportunities and interesting collaborations.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-24 sm:py-32 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-5 text-center">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-5">Let’s build something</h2>
      <p class="text-zinc-400 mb-10 max-w-md mx-auto">Have a project in mind or just want to say hi?</p>
      <a href="mailto:hello@two9.dev" class="inline-flex px-8 py-4 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition">
        hello@two9.dev
      </a>
      <div class="flex justify-center gap-8 mt-12 text-sm">
        <a href="#" class="hover:text-accent transition">GitHub</a>
        <a href="#" class="hover:text-accent transition">Twitter / X</a>
        <a href="#" class="hover:text-accent transition">LinkedIn</a>
      </div>
    </div>
  </section>

  <footer class="py-8 border-t border-white/5 text-center text-sm text-zinc-600">
    © 2026 TWO9. Built with intention.
  </footer>

  <script>
    // Mobile menu
    const menuBtn = document.getElementById('menuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    menuBtn?.addEventListener('click', () => mobileMenu.classList.toggle('hidden'));
    mobileMenu?.querySelectorAll('a').forEach(a => a.addEventListener('click', () => mobileMenu.classList.add('hidden')));

    // ===== STACKED CARDS LOGIC =====
    const container = document.getElementById('stackContainer');
    const cards = document.querySelectorAll('.stack-card');
    const totalCards = cards.length;

    function updateStack() {
      const rect = container.getBoundingClientRect();
      const containerTop = rect.top;
      const containerHeight = container.offsetHeight;
      const viewportHeight = window.innerHeight;

      // Progress from 0 → 1 while the sticky section is active
      let progress = -containerTop / (containerHeight - viewportHeight);
      progress = Math.min(Math.max(progress, 0), 1);

      cards.forEach((card, i) => {
        // How far this card is in the sequence
        const cardProgress = progress * (totalCards - 1) - i;

        // Clamp between -1 and 1
        let p = Math.min(Math.max(cardProgress, -1), 1);

        // Current card (on top)
        if (p <= 0) {
          // Coming in from bottom or fully visible
          const translateY = p * 80;          // slide up
          const scale = 1 + p * 0.05;
          const opacity = 1 + p * 0.3;

          card.style.transform = `translateY(${translateY}px) scale(${Math.max(scale, 0.9)})`;
          card.style.opacity = Math.max(opacity, 0.4);
          card.style.zIndex = totalCards - i;
        } else {
          // Already passed → move up and shrink (stacking behind)
          const translateY = -p * 40;
          const scale = 1 - p * 0.08;
          const opacity = 1 - p * 0.4;

          card.style.transform = `translateY(${translateY}px) scale(${scale})`;
          card.style.opacity = Math.max(opacity, 0.3);
          card.style.zIndex = totalCards - i;
        }
      });
    }

    window.addEventListener('scroll', updateStack, { passive: true });
    window.addEventListener('resize', updateStack);
    updateStack(); // initial call
  </script>
</body>
</html>
