<script>
  // Mobile menu
  const menuBtn = document.getElementById('menuBtn');
  const mobileMenu = document.getElementById('mobileMenu');
  menuBtn?.addEventListener('click', () => mobileMenu.classList.toggle('hidden'));
  mobileMenu?.querySelectorAll('a').forEach(a => a.addEventListener('click', () => mobileMenu.classList.add('hidden')));

  // ===== RGB GLOW (click + touch) - FIXED =====
  const cards = document.querySelectorAll('.stack-card');

  cards.forEach(card => {
    card.addEventListener('click', () => {
      // Turn off all others
      cards.forEach(c => c.classList.remove('rgb-active'));
      // Turn on current
      card.classList.add('rgb-active');
    });
  });

  // ===== STACKED CARDS + AUTO TURN OFF GLOW =====
  const container = document.getElementById('stackContainer');
  const totalCards = cards.length;
  let currentFront = 0;

  function updateStack() {
    const rect = container.getBoundingClientRect();
    const progress = Math.min(Math.max(-rect.top / (container.offsetHeight - window.innerHeight), 0), 1);

    // Which card is currently in front
    const frontIndex = Math.min(Math.floor(progress * (totalCards - 1) + 0.5), totalCards - 1);

    // If front card changed → remove glow from previous cards
    if (frontIndex !== currentFront) {
      cards.forEach(c => c.classList.remove('rgb-active'));
      currentFront = frontIndex;
    }

    cards.forEach((card, i) => {
      const cardProgress = progress * (totalCards - 1) - i;
      let p = Math.min(Math.max(cardProgress, -1), 1);

      if (p <= 0) {
        const translateY = p * 80;
        const scale = 1 + p * 0.05;
        card.style.transform = `translateY(${translateY}px) scale(${Math.max(scale, 0.9)})`;
        card.style.opacity = Math.max(1 + p * 0.3, 0.4);
      } else {
        const translateY = -p * 40;
        const scale = 1 - p * 0.08;
        card.style.transform = `translateY(${translateY}px) scale(${scale})`;
        card.style.opacity = Math.max(1 - p * 0.4, 0.3);
      }
      card.style.zIndex = totalCards - i;
    });
  }

  window.addEventListener('scroll', updateStack, { passive: true });
  window.addEventListener('resize', updateStack);
  updateStack();

  // ===== TV SLIDE =====
  const tvWrapper = document.getElementById('tvWrapper');
  const tvObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        tvWrapper.classList.add('visible');
      } else {
        tvWrapper.classList.remove('visible');
      }
    });
  }, { threshold: 0.15 });

  tvObserver.observe(tvWrapper);
</script>
