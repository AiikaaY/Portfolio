<template>
  <div class="nav-wrapper" :class="{ scrolled: isScrolled }">
    <nav>
      <div class="nav-logo" @click="scrollToHero" style="cursor: pointer;">OIB<span>.</span></div>

      <ul class="nav-links">
        <li><a href="#skills">Services</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#contact" class="nav-cta">Hire Me</a></li>
      </ul>

      <button
        class="nav-hamburger"
        :class="{ open: isOpen }"
        @click="toggleMenu"
        :aria-expanded="isOpen.toString()"
        aria-label="Toggle navigation"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </nav>

    <div class="nav-mobile" :class="{ open: isOpen }">
      <a href="#skills" @click="closeMenu">Services</a>
      <a href="#projects" @click="closeMenu">Projects</a>
      <a href="#contact" @click="closeMenu">Contact</a>
      <a href="#contact" class="mobile-cta" @click="closeMenu">Hire Me</a>
    </div>
  </div>

  <div class="nav-backdrop" :class="{ visible: isOpen }" @click="closeMenu"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isOpen = ref(false)

const scrollToHero = () => {
  closeMenu()
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 40
  if (isOpen.value) closeMenu()
}

const toggleMenu = () => { isOpen.value = !isOpen.value }
const closeMenu = () => { isOpen.value = false }

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.nav-wrapper {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
}

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.25rem 5%;
  background: rgba(255, 255, 255, 0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(11, 29, 58, 0.08);
  transition: box-shadow 0.3s var(--ease);
}

.nav-wrapper.scrolled nav {
  box-shadow: 0 2px 20px rgba(11, 29, 58, 0.1);
}

.nav-logo {
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--navy);
  letter-spacing: -0.02em;
}

.nav-logo span {
  color: var(--accent);
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  font-size: 1rem;
  font-weight: 500;
  color: var(--slate);
  text-decoration: none;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: var(--navy);
}

.nav-cta {
  background: var(--navy);
  color: var(--white) !important;
  padding: 0.5rem 1.25rem;
  border-radius: 6px;
  transition: background 0.2s;
}

.nav-cta:hover {
  background: var(--navy-light) !important;
}

/* Hamburger button */
.nav-hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 6px;
  border-radius: 6px;
  transition: background 0.2s;
}

.nav-hamburger:hover {
  background: var(--cloud);
}

.nav-hamburger span {
  display: block;
  width: 22px;
  height: 2px;
  background: var(--navy);
  border-radius: 2px;
  transition: transform 0.3s var(--ease), opacity 0.25s;
  transform-origin: center;
}

.nav-hamburger.open span:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}

.nav-hamburger.open span:nth-child(2) {
  opacity: 0;
  transform: scaleX(0);
}

.nav-hamburger.open span:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}

/* Mobile slide-down panel */
.nav-mobile {
  position: absolute;
  top: 100%;
  left: 0; right: 0;
  background: rgba(255, 255, 255, 0.98);
  backdrop-filter: blur(12px);
  display: flex;
  flex-direction: column;
  padding: 0.5rem 5% 1.5rem;
  border-bottom: 1px solid rgba(11, 29, 58, 0.08);
  box-shadow: 0 8px 32px rgba(11, 29, 58, 0.12);
  transform: translateY(-8px);
  opacity: 0;
  pointer-events: none;
  transition: transform 0.3s var(--ease), opacity 0.25s;
}

.nav-mobile.open {
  transform: translateY(0);
  opacity: 1;
  pointer-events: auto;
}

.nav-mobile a {
  font-size: 1.125rem;
  font-weight: 500;
  color: var(--slate);
  text-decoration: none;
  padding: 1rem 0;
  border-bottom: 1px solid rgba(11, 29, 58, 0.06);
  transition: color 0.2s;
}

.nav-mobile a:last-of-type {
  border-bottom: none;
}

.nav-mobile a:hover {
  color: var(--navy);
}

.mobile-cta {
  margin-top: 0.75rem;
  background: var(--navy) !important;
  color: var(--white) !important;
  padding: 0.9rem 1.5rem;
  border-radius: 8px;
  text-align: center;
  border-bottom: none !important;
  font-weight: 600;
  transition: background 0.2s;
}

.mobile-cta:hover {
  background: var(--navy-light) !important;
}

/* Backdrop overlay */
.nav-backdrop {
  position: fixed;
  inset: 0;
  z-index: 99;
  background: rgba(11, 29, 58, 0.25);
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s;
}

.nav-backdrop.visible {
  opacity: 1;
  pointer-events: auto;
}

@media (max-width: 768px) {
  .nav-links { display: none; }
  .nav-hamburger { display: flex; }
}
</style>
