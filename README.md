<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TWO9 — Portfolio</title>
  <script src="https://cdn.tailwindcss.com"></script>
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
            dark: '#0a0a0b',
            card: '#121214',
            accent: '#a3e635', // lime
          }
        }
      }
    }
  </script>
  <style>
    body { background: #0a0a0b; }
    .glow {
      box-shadow: 0 0 40px -10px rgba(163, 230, 53, 0.25);
    }
    .project-card:hover {
      transform: translateY(-4px);
      border-color: #a3e635;
    }
  </style>
</head>
<body class="font-sans text-zinc-300 antialiased">

  <!-- Navbar -->
  <nav class="fixed top-0 w-full z-50 bg-dark/80 backdrop-blur-md border-b border-white/5">
    <div class="max-w-5xl mx-auto px-6 h-16 flex items-center justify-between">
      <a href="#" class="font-display font-bold text-xl tracking-tight text-white">TWO9</a>
      <div class="hidden sm:flex gap-8 text-sm">
        <a href="#work" class="hover:text-accent transition">Work</a>
        <a href="#about" class="hover:text-accent transition">About</a>
        <a href="#contact" class="hover:text-accent transition">Contact</a>
      </div>
    </div>
  </nav>

  <!-- Hero -->
  <section class="min-h-screen flex items-center pt-16">
    <div class="max-w-5xl mx-auto px-6 w-full">
      <p class="text-accent font-medium mb-4 tracking-wide text-sm">Hey, I’m</p>
      <h1 class="font-display text-5xl sm:text-7xl font-bold text-white leading-none mb-6">
        TWO9
      </h1>
      <p class="text-xl sm:text-2xl text-zinc-400 max-w-xl leading-relaxed mb-10">
        Building clean digital experiences.<br>
        Developer • Designer • Creator
      </p>
      <div class="flex flex-wrap gap-4">
        <a href="#work" class="px-6 py-3 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition">
          View Work
        </a>
        <a href="#contact" class="px-6 py-3 border border-white/20 rounded-full hover:border-accent hover:text-accent transition">
          Get in touch
        </a>
      </div>
    </div>
  </section>

  <!-- Work -->
  <section id="work" class="py-24">
    <div class="max-w-5xl mx-auto px-6">
      <h2 class="font-display text-3xl font-bold text-white mb-12">Selected Work</h2>
      
      <div class="grid md:grid-cols-2 gap-6">
        <!-- Project 1 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-6 transition duration-300">
          <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project One</h3>
          <p class="text-zinc-400 text-sm mb-4">Short description of what you built and the impact it had.</p>
          <div class="flex gap-3 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">React</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Tailwind</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Next.js</span>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-6 transition duration-300">
          <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Two</h3>
          <p class="text-zinc-400 text-sm mb-4">Another cool thing you shipped. Keep it short and clear.</p>
          <div class="flex gap-3 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">TypeScript</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Node</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Postgres</span>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-6 transition duration-300">
          <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Three</h3>
          <p class="text-zinc-400 text-sm mb-4">Something experimental or personal that shows your style.</p>
          <div class="flex gap-3 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Framer Motion</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Three.js</span>
          </div>
        </div>

        <!-- Project 4 -->
        <div class="project-card bg-card border border-white/10 rounded-2xl p-6 transition duration-300">
          <div class="aspect-video bg-zinc-900 rounded-xl mb-5 flex items-center justify-center text-zinc-600">
            Project Image
          </div>
          <h3 class="text-xl font-semibold text-white mb-2">Project Four</h3>
          <p class="text-zinc-400 text-sm mb-4">One more strong project to fill the grid nicely.</p>
          <div class="flex gap-3 text-xs">
            <span class="px-2.5 py-1 bg-white/5 rounded-full">Python</span>
            <span class="px-2.5 py-1 bg-white/5 rounded-full">AI</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- About -->
  <section id="about" class="py-24 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-6">
      <div class="grid md:grid-cols-5 gap-12 items-start">
        <div class="md:col-span-2">
          <h2 class="font-display text-3xl font-bold text-white mb-6">About</h2>
          <div class="w-24 h-24 rounded-2xl bg-gradient-to-br from-accent/20 to-emerald-900/30 border border-accent/20 flex items-center justify-center text-2xl font-display font-bold text-accent">
            T9
          </div>
        </div>
        <div class="md:col-span-3 space-y-5 text-lg text-zinc-400 leading-relaxed">
          <p>
            I’m TWO9 — a developer who cares about clean code, sharp design, and products that feel good to use.
          </p>
          <p>
            I work across the stack but love the frontend the most: fast interfaces, smooth interactions, and thoughtful details.
          </p>
          <p>
            Currently open to new opportunities and interesting collaborations.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-24 border-t border-white/5">
    <div class="max-w-5xl mx-auto px-6 text-center">
      <h2 class="font-display text-3xl sm:text-4xl font-bold text-white mb-6">
        Let’s build something
      </h2>
      <p class="text-zinc-400 mb-10 max-w-md mx-auto">
        Have a project in mind or just want to say hi? Reach out anytime.
      </p>
      <a href="mailto:hello@two9.dev" class="inline-flex items-center gap-2 px-8 py-4 bg-accent text-dark font-semibold rounded-full hover:bg-lime-400 transition glow">
        hello@two9.dev
      </a>
      
      <div class="flex justify-center gap-6 mt-12 text-sm">
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

</body>
</html># Two9-portfolio
