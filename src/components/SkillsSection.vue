<template>
  <section id="skills">
    <div class="skills-header reveal">
      <span class="section-tag">Sounds Familiar?</span>
      <h2 class="section-title">These Are The Problems I Help You Fix</h2>
      <p class="section-sub">
       You have a real business. A real product. A real service. But something about your online presence isn't reflecting that. Here's where I come in.
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
    desc: 'You have put in the work to build something real. Your business deserves a website that shows that. One that makes the right people stop, trust you instantly, and reach out without second guessing.',
    tags: ['Marketing sites', 'Product pages', 'Figma handoff']
  },
  {
    name: 'Landing Page Design',
    // icon: '🚀',
    desc: "You have an offer worth paying for but nowhere online that actually sells it. People are hearing about you but when they look you up nothing is compelling them to take action. I build you a focused landing page that turns visitors into paying customers.",
    tags: ['Product launches', 'Waitlists', 'Campaign pages']
  },
  {
    name: 'App & Mobile UI',
    // icon: '📱',
    desc: 'Your app works the way it should but the moment someone opens it they are not impressed. A poor interface makes people doubt the product regardless of how good it is. I design mobile and app interfaces that feel intuitive, polished, and worth using.',
    tags: ['iOS & Android UI', 'Web app design', 'User flows']
  },
  {
    name: 'Brand & Visual Identity',
    // icon: '🎨',
    desc: 'When people see your business online they should immediately know what you stand for and feel something. If your visuals are inconsistent, forgettable, or just thrown together, you are losing trust before you even say a word. I create a visual identity that makes your brand look like it means business.',
    tags: ['Logo design', 'Colour & type', 'Brand guidelines']
  },
  {
    name: 'UI/UX Consulting',
    // icon: '💬',
    desc: `You have something built already but it is not doing what you expected People visit and leave. They sign up but don't convert. Something in the experience is breaking the journey and you can't put your finger on it. I come in, identify exactly what is pushing people away and tell you how to fix it.`,
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
  font-size: 30px;
}
.section-sub {
  font-weight: 500;
  font-size: 19px;
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