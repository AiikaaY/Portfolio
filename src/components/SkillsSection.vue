<template>
  <section id="skills">
    <div class="skills-header reveal">
      <span class="section-tag">Expertise</span>
      <h2 class="section-title">Services I Offer</h2>
      <p class="section-sub">
        A focused set of design services built for brands and founders who care about how their product looks and feels.
      </p>
    </div>

    <div class="services-layout">
      <div class="service-list">
        <div
          v-for="(service, i) in services"
          :key="service.name"
          class="service-item"
          :class="{ active: active === i }"
          @click="active = i"
        >
          <div class="service-item-left">
            <!-- <span class="service-num">0{{ i + 1 }}</span> -->
            <span class="service-name">{{ service.name }}</span>
          </div>
          <span class="service-arrow">+</span>
        </div>
      </div>

      <div class="service-detail">
        <Transition name="fade" mode="out-in">
          <div :key="active" class="detail-inner">
            <!-- <div class="detail-icon">{{ services[active].icon }}</div> -->
            <h3 class="detail-title">{{ services[active].name }}</h3>
            <p class="detail-desc">{{ services[active].desc }}</p>
            <div class="detail-tags">
              <span v-for="tag in services[active].tags" :key="tag" class="tag">{{ tag }}</span>
            </div>
          </div>
        </Transition>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const active = ref(0)

const services = [
  {
    name: 'Website Design',
    // icon: '🌐',
    desc: 'Multi-page marketing or product websites built to communicate clearly and convert. From information architecture to polished visuals and developer handoff.',
    tags: ['Marketing sites', 'Product pages', 'Figma handoff']
  },
  {
    name: 'Landing Page Design',
    // icon: '🚀',
    desc: "Single-page experiences built to convert — whether that's a product launch, a waitlist, or a campaign. Every element earns its place.",
    tags: ['Product launches', 'Waitlists', 'Campaign pages']
  },
  {
    name: 'App & Mobile UI',
    // icon: '📱',
    desc: 'Intuitive interfaces for mobile and web apps. Designed around real user flows — not just pretty screens, but screens that actually work.',
    tags: ['iOS & Android UI', 'Web app design', 'User flows']
  },
  {
    name: 'Brand & Visual Identity',
    // icon: '🎨',
    desc: 'Logos, colour systems, typography — the visual language that ties a brand together. Built to last and scale across every touchpoint.',
    tags: ['Logo design', 'Colour & type', 'Brand guidelines']
  },
  {
    name: 'UI/UX Consulting',
    // icon: '💬',
    desc: 'Design audits, product reviews, and strategic direction for teams who want an outside perspective on their product experience.',
    tags: ['Design audits', 'Product strategy', 'UX reviews']
  }
]
</script>

<style scoped>
section {
  background: var(--white);
}

.skills-header {
  margin-bottom: 3rem;
}

.section-title {
  font-weight: 600;
}
.section-sub {
  font-weight: 500;
}

.services-layout {
  display: grid;
  grid-template-columns: 1fr 1.4fr;
  gap: 0 3rem;
  align-items: start;
}

.service-list {
  display: flex;
  flex-direction: column;
}

.service-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.1rem 0;
  border-bottom: 1px solid rgba(11, 29, 58, 0.08);
  cursor: pointer;
  transition: padding-left 0.2s;
}

.service-item:first-child {
  border-top: 1px solid rgba(11, 29, 58, 0.08);
}

.service-item-left {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.service-num {
  font-size: 11px;
  font-weight: 600;
  color: #a0aec0;
  letter-spacing: 0.05em;
  min-width: 20px;
}

.service-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--slate);
  transition: color 0.15s;
}

.service-item.active .service-name {
  color: var(--navy);
}

.service-item.active {
  padding-left: 4px;
}

.service-arrow {
  font-size: 20px;
  color: #a0aec0;
  transition: transform 0.2s, color 0.15s;
  line-height: 1;
}

.service-item.active .service-arrow {
  transform: rotate(45deg);
  color: var(--navy);
}

.service-detail {
  background: var(--cloud);
  border-radius: 16px;
  padding: 2rem;
  border: 1px solid rgba(11, 29, 58, 0.07);
  min-height: 200px;
}

.detail-icon {
  font-size: 28px;
  margin-bottom: 1rem;
}

.detail-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--navy);
  margin-bottom: 0.6rem;
}

.detail-desc {
  font-size: 1rem;
  color: var(--slate);
  line-height: 1.7;
  margin-bottom: 1.25rem;
  font-weight: 500;
}

.detail-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  font-weight: 500;
}

.tag {
  font-size: 14px;
  font-weight: 500;
  background: var(--white);
  border: 1px solid rgba(11, 29, 58, 0.1);
  border-radius: 999px;
  padding: 4px 12px;
  color: var(--slate);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.15s ease, transform 0.15s ease;
}

.fade-enter-from {
  opacity: 0;
  transform: translateY(6px);
}

.fade-leave-to {
  opacity: 0;
  transform: translateY(-6px);
}

@media (max-width: 768px) {
  .services-layout {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
</style>