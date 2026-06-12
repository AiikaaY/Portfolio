<template>
  <section class="hero" id="home">
    <div class="hero-left">
      <div class="hero-badge">Frontend Developer</div>
      <h1>Building interfaces that <em>work</em> and impress.</h1>
      <p class="hero-desc">
        Businesses don't just need a website. They need one that works. I build clean, 
        high-performance web experiences that help businesses across the world look credible, 
        convert visitors, and compete at the highest level.
      </p>
      <div class="hero-actions">
        <a href="#projects" class="btn-primary">
          View My Work
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </a>
        <a href="#contact" class="btn-outline">Get In Touch</a>
      </div>

      <div class="value-props">
        <div class="vp-item">
          <div class="vp-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
              <path d="M13 10V3L4 14h7v7l9-11h-7z"/>
            </svg>
          </div>
          <div>
            <div class="vp-label">Fast Delivery</div>
            <div class="vp-sub">On time, every time</div>
          </div>
        </div>
        <div class="vp-item">
          <div class="vp-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
              <rect x="5" y="2" width="14" height="20" rx="2"/>
              <path d="M12 18h.01"/>
            </svg>
          </div>
          <div>
            <div class="vp-label">Mobile-First</div>
            <div class="vp-sub">Works on all screens</div>
          </div>
        </div>
        <div class="vp-item">
          <div class="vp-icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="16 18 22 12 16 6"/>
              <polyline points="8 6 2 12 8 18"/>
            </svg>
          </div>
          <div>
            <div class="vp-label">Clean Code</div>
            <div class="vp-sub">Maintainable & scalable</div>
          </div>
        </div>
      </div>
    </div>

    <div class="hero-right">
      <div class="hero-card">
        <div class="card-avatar">OB</div>
        <div class="card-name">Osemwegie Best</div>
        <div class="card-role">Frontend Developer</div>
        <div class="card-skills">
          <span class="skill-tag">HTML & CSS</span>
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">Vue.js</span>
          <span class="skill-tag">Responsive Design</span>
          <span class="skill-tag">UI/UX</span>
        </div>
        <div class="card-divider"></div>
        <div class="card-available">
          <div class="pulse-dot"></div>
          Available for new projects
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  padding: 8rem 5% 5rem;
  gap: 4rem;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: -200px; right: -200px;
  width: 600px; height: 600px;
  background: radial-gradient(circle, rgba(37,99,235,0.06) 0%, transparent 70%);
  border-radius: 50%;
  pointer-events: none;
}

.hero-left {
  animation: fadeUp 0.8s var(--ease) both;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: var(--accent-soft);
  color: var(--accent);
  font-size: 1rem;
  font-weight: 600;
  padding: 0.4rem 1rem;
  border-radius: 100px;
  margin-bottom: 1.5rem;
  letter-spacing: 0.04em;
  text-transform: uppercase;
}

.hero-badge::before {
  content: '';
  width: 6px; height: 6px;
  background: var(--accent);
  border-radius: 50%;
  display: block;
}

h1 {
  font-size: clamp(1.875rem, 4vw, 3.25rem);
  font-weight: 600;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--navy);
  margin-bottom: 1.25rem;
}

h1 em {
  font-style: normal;
  color: var(--accent);
}

.hero-desc {
  font-size: 1.195rem;
  color: var(--slate);
  line-height: 1.75;
  margin-bottom: 2rem;
  max-width: 420px;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  align-items: center;
  margin-bottom: 2.5rem;
}

.btn-primary {
  background: var(--navy);
  color: var(--white);
  padding: 0.875rem 2rem;
  border-radius: 8px;
  font-size: 1.125rem;
  font-weight: 600;
  text-decoration: none;
  font-family: var(--font);
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  transition: background 0.2s var(--ease), transform 0.15s;
}

.btn-primary:hover {
  background: var(--navy-light);
  transform: translateY(-1px);
}

.btn-outline {
  background: transparent;
  color: var(--navy);
  padding: 0.875rem 2rem;
  border-radius: 8px;
  font-size: 1.125rem;
  font-weight: 600;
  text-decoration: none;
  font-family: var(--font);
  border: 1.5px solid var(--silver);
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  transition: border-color 0.2s, background 0.2s;
}

.btn-outline:hover {
  border-color: var(--navy);
  background: var(--cloud);
}

.value-props {
  display: flex;
  border: 1px solid rgba(11,29,58,0.1);
  border-radius: 12px;
  overflow: hidden;
  background: var(--white);
}

.vp-item {
  flex: 1;
  padding: 1rem 1.25rem;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  border-right: 1px solid rgba(11,29,58,0.08);
}

.vp-item:last-child {
  border-right: none;
}

.vp-icon {
  width: 34px; height: 34px;
  border-radius: 8px;
  background: var(--accent-soft);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  color: var(--accent);
}

.vp-icon svg {
  width: 16px; height: 16px;
}

.vp-label {
  font-size: 1rem;
  font-weight: 600;
  color: var(--navy);
  line-height: 1.3;
}

.vp-sub {
  font-size: 1rem;
  color: var(--slate-light);
  margin-top: 0.1rem;
}

.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeUp 0.8s 0.2s var(--ease) both;
}

.hero-card {
  background: var(--navy);
  border-radius: 20px;
  padding: 2.5rem;
  width: 100%;
  max-width: 380px;
  position: relative;
  overflow: hidden;
}

.hero-card::before {
  content: '';
  position: absolute;
  top: -60px; right: -60px;
  width: 200px; height: 200px;
  background: rgba(37,99,235,0.25);
  border-radius: 50%;
}

.hero-card::after {
  content: '';
  position: absolute;
  bottom: -40px; left: -40px;
  width: 150px; height: 150px;
  background: rgba(201,168,76,0.15);
  border-radius: 50%;
}

.card-avatar {
  width: 68px; height: 68px;
  border-radius: 16px;
  background: linear-gradient(135deg, var(--accent) 0%, #1d4ed8 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.75rem;
  font-weight: 600;
  color: white;
  margin-bottom: 1.25rem;
  position: relative;
  z-index: 1;
}

.card-name {
  font-size: 1.375rem;
  font-weight: 700;
  color: var(--white);
  letter-spacing: -0.01em;
  margin-bottom: 0.25rem;
  position: relative;
  z-index: 1;
}

.card-role {
  font-size: 1rem;
  color: rgba(255,255,255,0.5);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-bottom: 1.75rem;
  position: relative;
  z-index: 1;
}

.card-skills {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  position: relative;
  z-index: 1;
}

.skill-tag {
  background: rgba(255,255,255,0.1);
  color: rgba(255,255,255,0.85);
  padding: 0.375rem 0.875rem;
  border-radius: 6px;
  font-size: 1rem;
  font-weight: 500;
  border: 1px solid rgba(255,255,255,0.12);
}

.card-divider {
  height: 1px;
  background: rgba(255,255,255,0.1);
  margin: 1.5rem 0;
  position: relative;
  z-index: 1;
}

.card-available {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 1rem;
  color: rgba(255,255,255,0.7);
  position: relative;
  z-index: 1;
}

.pulse-dot {
  width: 8px; height: 8px;
  background: #22c55e;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.6; transform: scale(1.3); }
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
    padding-top: 7rem;
    gap: 2rem;
  }

  .hero-right { display: none; }

  .value-props { flex-direction: column; }

  .vp-item {
    border-right: none;
    border-bottom: 1px solid rgba(11,29,58,0.08);
  }

  .vp-item:last-child { border-bottom: none; }
}
</style>
