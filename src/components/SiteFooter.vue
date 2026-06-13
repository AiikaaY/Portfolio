<template>
  <footer>
    <div class="footer-logo">OIB<span>.</span></div>

    <div class="footer-social">
      <a href="http://www.linkedin.com/in/ikponmwosa-osemwegie-988679323" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">
        <svg viewBox="0 0 24 24" fill="currentColor">
          <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
        </svg>
      </a>
      <a href="https://x.com/aiikaayy?s=11" target="_blank" rel="noopener noreferrer" aria-label="Twitter / X">
        <svg viewBox="0 0 24 24" fill="currentColor">
          <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.747l7.73-8.835L2.144 2.25h6.961l4.265 5.638 4.874-5.638zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
        </svg>
      </a>
    </div>

    <span class="footer-copy">&copy; {{ year }} Osemwegie Best</span>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
footer {
  background: #071526;
  padding: 2rem 5%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-top: 1px solid rgba(255,255,255,0.06);
}

.footer-logo {
  font-size: 1.125rem;
  font-weight: 700;
  color: rgba(255,255,255,0.35);
  letter-spacing: -0.02em;
}

.footer-logo span {
  color: var(--accent);
  opacity: 0.7;
}

.footer-social {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.footer-social a {
  width: 38px;
  height: 38px;
  border-radius: 8px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255,255,255,0.4);
  transition: background 0.2s, color 0.2s, border-color 0.2s;
}

.footer-social a:hover {
  background: rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.85);
  border-color: rgba(255,255,255,0.2);
}

.footer-social svg {
  width: 17px;
  height: 17px;
}

.footer-copy {
  font-size: 1rem;
  color: rgba(255,255,255,0.25);
  font-weight: 500;
}

@media (max-width: 768px) {
  footer {
    flex-direction: column;
    gap: 1.25rem;
    text-align: center;
  }
}
</style>
