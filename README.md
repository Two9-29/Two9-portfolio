<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TWO9 — Portfolio</title>

  <!-- Tailwind -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
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
    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: #09090b;
      overflow-x: hidden;
    }

    /* Animations */
    .fade-up {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.7s cubic-bezier(0.16, 1, 0.3, 1);
    }

    .fade-up.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .project-card {
      transition: all 0.3s ease;
    }

    .project-card:hover {
      transform: translateY(-6px);
      border-color: #a3e635;
      box-shadow: 0 10px 30px -10px rgba(163, 230, 53, 0.15);
    }

    .nav-blur {
      backdrop-filter: blur(12px);
      background: rgba(9, 9, 11, 0.8);
    }
  </style>
</head>
<body class="font-sans text-zinc-300 antialiased">

  <!-- Navbar -->
  <nav class="fixed top-0 w-full z-50 nav-blur border-b border-white/5">
    <div class="max-w-5xl mx-auto px-5 h-16 flex items-center justify-between">
      <a href="#" class="font-display font-bold text-xl tracking-tight text-white">TWO9</a>
      
      <div class="hidden sm:flex items-center gap-8 text-sm">
        <a href="#work" class="hover:text-accent transition">Work</a>
        <a href="#about" class="hover:text-accent transition">About</a>
        <a href="#contact" class="hover:text-accent transition">Contact</a>
      </div>

      <!-- Mobile menu button -->
      <button id="menuBtn" class="sm:hidden text-white p-2">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>

    <!-- Mobile menu -->
    <div id="mobileMenu" class="hidden sm:hidden border-t border-white/5 bg-dark">
      <div class="flex flex-col px-5 py-4 gap-4 text-sm">
        <a href="#work" class="hover:text-accent">Work</a>
        <a href="#about" class="hover:text-accent">About</a>
        <a href="#contact" class="hover:text-accent">Contact</a>
      </div>
    </div>
  </nav>

  <!-- Hero -->
  <section class="min-h-screen flex items-center pt-20 pb-16">
    <div class="max-w-5xl mx-auto px-5 w-full">
      <p class="text-accent font-medium mb-3 tracking-wide text-sm fade-up">Hey, I’m</p>
      
      <h1 class="font-display text-5xl sm:text-7xl font-bold text-white leading-none mb-6 fade-up" style="transition-delay: 0.1s">
        TWO9
      </h1>
      
      <p class="text-lg sm:text-2xl text-zinc-400 max-w-xl leading-relaxed mb-10 fade-up" style="transition-delay: 0.2s">
        Building clean digital experiences.<br class="hidden sm:block">
        Developer • Designer • Creator
      </p>
      
      <div class="flex flex-wrap gap-4 fade-up" style="transition-delay: 0.3s">
        <a href="#work" class="px-7 py-3.5 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition active:scale-95">
          View Work
        </a>
        <a href="#contact" class="px-7 py-3.5 border border-white/20 rounded-full hover:border-accent hover:text-accent transition active:scale-95">
          Get in touch
        </a>
      </div>
    </div>
  </section>

  <!-- Work -->
  <section id="work" class="py-20 sm:py-28">
    <div class="max-w-5xl mx-auto px-5">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-10 fade-up">Selected Work</h2>
      
      <div class="grid sm:grid-cols-2 gap-5 sm:gap-6">
        
        <!-- Project 1 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-5 sm:p-6 fade-up">
          <div class="aspect-video bg-zinc-900/80 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project One</h3>
          <p class="text-zinc-400 text-sm mb-4 leading-relaxed">Short description of what you built and the impact it had.</p>
          <div class="flex flex-wrap gap-2 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">React</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Tailwind</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Next.js</span>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-5 sm:p-6 fade-up" style="transition-delay: 0.1s">
          <div class="aspect-video bg-zinc-900/80 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Two</h3>
          <p class="text-zinc-400 text-sm mb-4 leading-relaxed">Another cool thing you shipped. Keep it short and clear.</p>
          <div class="flex flex-wrap gap-2 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">TypeScript</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Node</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Postgres</span>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-5 sm:p-6 fade-up" style="transition-delay: 0.15s">
          <div class="aspect-video bg-zinc-900/80 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Three</h3>
          <p class="text-zinc-400 text-sm mb-4 leading-relaxed">Something experimental that shows your personal style.</p>
          <div class="flex flex-wrap gap-2 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Framer Motion</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Three.js</span>
          </div>
        </div>

        <!-- Project 4 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-5 sm:p-6 fade-up" style="transition-delay: 0.2s">
          <div class="aspect-video bg-zinc-900/80 rounded-xl mb-5 flex items-center justify-center text-zinc-600 text-sm">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Four</h3>
          <p class="text-zinc-400 text-sm mb-4 leading-relaxed">One more strong project to complete the grid.</p>
          <div class="flex flex-wrap gap-2 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Python</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">AI</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- About -->
  <section id="about" class="py-20 sm:py-28 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-5">
      <div class="grid md:grid-cols-5 gap-10 md:gap-16 items-start">
        <div class="md:col-span-2 fade-up">
          <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-8">About</h2>
          <div class="w-24 h-24 rounded-2xl bg-gradient-to-br from-accent/20 to-emerald-900/20 border border-accent/20 flex items-center justify-center text-2xl font-display font-bold text-accent">
            T9
          </div>
        </div>
        <div class="md:col-span-3 space-y-5 text-base sm:text-lg text-zinc-400 leading-relaxed fade-up" style="transition-delay: 0.1s">
          <p>I’m TWO9 — a developer who cares about clean code, sharp design, and products that feel good to use.</p>
          <p>I work across the stack but love the frontend the most: fast interfaces, smooth interactions, and thoughtful details.</p>
          <p>Currently open to new opportunities and interesting collaborations.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-20 sm:py-28 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-5 text-center">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-5 fade-up">
        Let’s build something
      </h2>
      <p class="text-zinc-400 mb-10 max-w-md mx-auto fade-up" style="transition-delay: 0.1s">
        Have a project in mind or just want to say hi? Reach out anytime.
      </p>
      
      <a href="mailto:hello@two9.dev" 
         class="inline-flex items-center gap-2 px-8 py-4 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition fade-up"
         style="transition-delay: 0.2s">
        hello@two9.dev
      </a>
      
      <div class="flex justify-center gap-8 mt-12 text-sm fade-up" style="transition-delay: 0.3s">
        <a href="#" class="hover:text-accent transition">GitHub</a>
        <a href="#" class="hover:text-accent transition">Twitter / X</a>
        <a href="#" class="hover:text-accent transition">LinkedIn</a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-8 border-t border-white/5 text-center text-sm text-zinc-600">
    © 2026 TWO9. Built with intention.
  </footer>

  <script>
    // Mobile menu toggle
    const menuBtn = document.getElementById('menuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    
    menuBtn.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });

    // Close mobile menu when clicking a link
    mobileMenu.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        mobileMenu.classList.add('hidden');
      });
    });

    // Fade-up animation on scroll
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, {
      threshold: 0.15
    });

    document.querySelectorAll('.fade-up').forEach(el => {
      observer.observe(el);
    });

    // Make hero elements visible immediately
    setTimeout(() => {
      document.querySelectorAll('section:first-of-type .fade-up').forEach(el => {
        el.classList.add('visible');
      });
    }, 100);
  </script>
</body>
</html>
