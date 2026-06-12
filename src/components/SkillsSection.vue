<template>
  <section id="skills">
    <div class="skills-header reveal">
      <span class="section-tag">Expertise</span>
      <h2 class="section-title">What I Work With</h2>
      <p class="section-sub">
        A focused toolkit built for delivering modern, performant websites that work for your business.
      </p>
    </div>

    <div class="skills-grid">
      <div class="skill-group reveal">
        <div class="group-label">Core Stack</div>
        <ul>
          <li v-for="item in stack" :key="item">
            <svg viewBox="0 0 16 16" fill="none" width="14" height="14">
              <path d="M3 8l3.5 3.5L13 4" stroke="var(--accent)" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            {{ item }}
          </li>
        </ul>
      </div>

      <div class="skill-group reveal">
        <div class="group-label">What I Deliver</div>
        <ul>
          <li v-for="item in deliverables" :key="item">
            <svg viewBox="0 0 16 16" fill="none" width="14" height="14">
              <path d="M3 8l3.5 3.5L13 4" stroke="var(--accent)" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            {{ item }}
          </li>
        </ul>
      </div>

      <div class="skill-group reveal">
        <div class="group-label">Tools</div>
        <ul>
          <li v-for="item in tools" :key="item">
            <svg viewBox="0 0 16 16" fill="none" width="14" height="14">
              <path d="M3 8l3.5 3.5L13 4" stroke="var(--accent)" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
const stack = ['HTML5', 'CSS3', 'JavaScript (ES6+)', 'Vue.js']
const deliverables = ['Responsive Design', 'Mobile-First Dev', 'UI / UX', 'Performance Optimisation', 'Clean, Maintainable Code']
const tools = ['Git & GitHub', 'Figma', 'VS Code', 'Chrome DevTools']
</script>

<style scoped>
section {
  background: var(--white);
}

.skills-header {
  margin-bottom: 3rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

.skill-group {
  background: var(--cloud);
  border-radius: 16px;
  padding: 2rem;
  border: 1px solid rgba(11, 29, 58, 0.07);
}
.section-title{
  font-weight: 600;
}
.group-label {
  font-size: 1rem;
  font-weight: 600;
  color: var(--navy);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 1.25rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid rgba(11, 29, 58, 0.1);
}

ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.875rem;
}

li {
  display: flex;
  align-items: center;
  gap: 0.625rem;
  font-size: 1rem;
  font-weight: 500;
  color: var(--slate);
}

li svg {
  flex-shrink: 0;
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
