<template>
  <section id="projects">
    <div class="projects-header reveal">
      <span class="section-tag">Portfolio</span>
      <h2 class="section-title">Selected Projects</h2>
      <p class="section-sub">A closer look at problems I've solved and how I solved them.</p>
    </div>

    <div class="projects-grid">
      <div v-for="(project, index) in projects" :key="index" class="project-card reveal" :style="{ transitionDelay: index * 0.12 + 's' }">
        <div class="project-image">
          <div class="project-image-inner">
            <div v-if="project.live" class="browser-mockup">
              <div class="browser-bar">
                <div class="dot d1"></div>
                <div class="dot d2"></div>
                <div class="dot d3"></div>
                <div class="browser-url">
                  <span class="url-text">{{ project.url }}</span>
                </div>
              </div>
              <div class="browser-content">
                <div>
                  <div class="browser-title">{{ project.name }}</div>
                  <div class="browser-tagline">{{ project.type }}</div>
                </div>
              </div>
            </div>

            <div v-else class="coming-soon">
              <div class="cs-icon">
                <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
                  <path d="M10 4v12M4 10h12" stroke="rgba(255,255,255,0.4)" stroke-width="1.5" stroke-linecap="round"/>
                </svg>
              </div>
              <span class="cs-label">More coming soon</span>
            </div>

            <div v-if="project.live" class="project-type-badge">Live</div>
          </div>
        </div>

        <div class="project-body" :class="{ dimmed: !project.live }">
          <div class="project-name">{{ project.name }}</div>
          <p class="project-desc">{{ project.description }}</p>
          <div class="project-tags">
            <span v-for="tag in project.tags" :key="tag" class="project-tag">{{ tag }}</span>
          </div>
          <a v-if="project.live" :href="project.href" target="_blank" rel="noopener noreferrer" class="project-link">
            Visit Live Site
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none">
              <path d="M2 7h10M8 3l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    name: 'TrueTones',
    type: 'Skincare Brand · Landing Page',
    url: 'truetones.com.ng',
    href: 'https://www.truetones.com.ng',
    description: 'Dr Oghosa needed a website that felt as premium as her expertise. I designed a landing page that speaks directly to her audience, communicates her specialisms clearly, and gives first-time visitors an immediate reason to book.',
    tags: ['Landing Page', 'Brand Identity'],
    live: true,
  },
  {
    name: 'RideWithCruz',
    type: 'Mobility Startup · Full Website',
    url: 'ridewithcruz.com',
    href: 'https://www.ridewithcruz.com',
    description: 'Cruz is redefining urban mobility in Nigeria but needed a web presence that matched that ambition. I built a multi-page website covering passengers, drivers, and rentals, designed to build trust and drive both app downloads and driver sign-ups.',
    tags: ['Website Design', 'Mobile UI'],
    live: true,
  },
]
</script>

<style scoped>
section {
  background: var(--cloud);
}
.section-title{
  font-weight: 600;
}
.section-sub {
  font-weight: 500;
}
.projects-header {
  margin-bottom: 3rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
}

.project-card {
  background: var(--white);
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid rgba(11,29,58,0.08);
  transition: transform 0.3s var(--ease), box-shadow 0.3s var(--ease);
}

.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 48px rgba(11,29,58,0.12);
}

.project-image {
  height: 220px;
  background: var(--navy);
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.project-image-inner {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.browser-mockup {
  width: 85%;
  background: rgba(255,255,255,0.08);
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.12);
}

.browser-bar {
  background: rgba(255,255,255,0.06);
  padding: 0.5rem 0.75rem;
  display: flex;
  align-items: center;
  gap: 0.4rem;
  border-bottom: 1px solid rgba(255,255,255,0.08);
}

.dot { width: 8px; height: 8px; border-radius: 50%; }
.d1 { background: #ff5f56; }
.d2 { background: #febc2e; }
.d3 { background: #27c93f; }

.browser-url {
  flex: 1;
  background: rgba(255,255,255,0.08);
  border-radius: 4px;
  height: 24px;
  margin-left: 0.5rem;
  display: flex;
  align-items: center;
  padding: 0 0.5rem;
}

.url-text {
  font-size: 1rem;
  color: rgba(255,255,255,0.45);
  white-space: nowrap;
  overflow: hidden;
}

.browser-content {
  height: 120px;
  background: linear-gradient(160deg, rgba(37,99,235,0.2) 0%, rgba(11,29,58,0.5) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1rem;
  text-align: center;
}

.browser-title {
  font-size: 1rem;
  font-weight: 700;
  color: rgba(255,255,255,0.9);
  margin-bottom: 0.25rem;
}

.browser-tagline {
  font-size: 1rem;
  color: rgba(255,255,255,0.45);
  font-weight: 500;
}

.coming-soon {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
}

.cs-icon {
  width: 48px; height: 48px;
  border-radius: 12px;
  background: rgba(255,255,255,0.08);
  border: 1.5px dashed rgba(255,255,255,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
}

.cs-label {
  font-size: 1rem;
  color: rgba(255,255,255,0.35);
  font-weight: 500;
}

.project-type-badge {
  position: absolute;
  top: 1rem; right: 1rem;
  background: rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.8);
  font-size: 1rem;
  font-weight: 600;
  padding: 0.35rem 0.875rem;
  border-radius: 100px;
  border: 1px solid rgba(255,255,255,0.15);
  letter-spacing: 0.03em;
  text-transform: uppercase;
}

.project-body {
  padding: 1.5rem;
}

.project-body.dimmed {
  opacity: 0.55;
  pointer-events: none;
}

.project-name {
  font-size: 1.375rem;
  font-weight: 700;
  color: var(--navy);
  letter-spacing: -0.015em;
  margin-bottom: 0.35rem;
}

.project-desc {
  font-size: 1rem;
  color: var(--slate);
  line-height: 1.65;
  margin-bottom: 1.25rem;
  font-weight: 500;
}

.project-tags {
  display: flex;
  gap: 0.4rem;
  flex-wrap: wrap;
  margin-bottom: 1.25rem;
}

.project-tag {
  background: var(--accent-soft);
  color: var(--accent);
  font-size: 1rem;
  font-weight: 600;
  padding: 0.3rem 0.875rem;
  border-radius: 100px;
  letter-spacing: 0.02em;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  font-size: 1rem;
  font-weight: 600;
  color: var(--accent);
  text-decoration: none;
  transition: gap 0.2s;
}

.project-link:hover {
  gap: 0.65rem;
}
</style>
