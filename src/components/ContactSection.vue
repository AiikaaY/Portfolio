<template>
  <section id="contact">
    <div class="contact-inner">
      <div class="contact-left reveal">
        <span class="section-tag">Let's Work Together</span>
        <h2 class="section-title">Have a project in mind?</h2>
        <p class="section-sub">
          I build clean, professional websites for businesses that want to make an impact.
          Reach out via email or WhatsApp — I respond fast.
        </p>

        <div class="contact-methods">
          <a href="mailto:osemwegiebest@gmail.com" class="contact-method">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <path d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0l-9.75 6.75L2.25 6.75"/>
              </svg>
            </div>
            <div>
              <div class="cm-label">Email</div>
              <div class="cm-value">osemwegiebest@gmail.com</div>
            </div>
          </a>

          <a href="https://wa.me/2348157741603" target="_blank" rel="noopener noreferrer" class="contact-method">
            <div class="contact-icon wa-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <path d="M12 2C6.477 2 2 6.477 2 12c0 1.89.525 3.66 1.438 5.168L2 22l4.979-1.406A9.953 9.953 0 0012 22c5.523 0 10-4.477 10-10S17.523 2 12 2z"/>
                <path d="M8.5 9.5c0-.5.5-2 2-2 .5 0 1 .5 1.5 1.5s1 2 1 2.5c0 .5-.5 1-1 1.5-.3.3-.4.6-.2.9.5.8 1.3 1.7 2.2 2.2.3.2.6.1.9-.2.5-.5 1-1 1.5-1 .5 0 1.5.5 2 1s.5 1.5 0 2c-.8.8-2 1.5-3.5 1.5C11 19 8 16 7 13c-.5-1.5 0-2.7.8-3.5z"/>
              </svg>
            </div>
            <div>
              <div class="cm-label">WhatsApp</div>
              <div class="cm-value wa-value">+234 815 774 1603</div>
            </div>
          </a>

          <div class="contact-method static">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <path d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"/>
                <path d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"/>
              </svg>
            </div>
            <div>
              <div class="cm-label">Location</div>
              <div class="cm-value">Lagos, Nigeria</div>
            </div>
          </div>
        </div>
      </div>

      <div class="contact-form reveal">
        <div class="form-row">
          <label>Your Name</label>
          <input v-model="form.name" type="text" placeholder="John Doe"/>
        </div>
        <div class="form-row">
          <label>Email Address</label>
          <input v-model="form.email" type="email" placeholder="john@example.com"/>
        </div>
        <div class="form-row">
          <label>Message</label>
          <textarea v-model="form.message" placeholder="Tell me about your project..."></textarea>
        </div>
        <p v-if="formError" class="form-error">{{ formError }}</p>
        <button class="form-submit" @click="handleSubmit">
          <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18">
            <path d="M12 2C6.477 2 2 6.477 2 12c0 1.89.525 3.66 1.438 5.168L2 22l4.979-1.406A9.953 9.953 0 0012 22c5.523 0 10-4.477 10-10S17.523 2 12 2zm4.94 13.47c-.207.583-1.215 1.112-1.66 1.18-.447.065-.868.32-2.91-.61-2.456-1.14-4.02-3.63-4.14-3.8-.12-.17-.98-1.305-.98-2.49 0-1.185.62-1.768.84-2.01.22-.24.48-.3.64-.3l.46.008c.148.006.346-.057.54.413.207.497.7 1.72.762 1.844.063.124.105.27.02.432-.083.163-.124.265-.247.41l-.37.432c-.124.12-.252.25-.108.49.144.24.638 1.053 1.37 1.705.94.836 1.734 1.095 1.98 1.217.246.123.39.103.534-.062l.757-.897c.143-.185.286-.154.48-.093.193.063 1.227.58 1.437.685.21.106.35.16.4.247.05.09.05.52-.157 1.103z"/>
          </svg>
          Send via WhatsApp
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({ name: '', email: '', message: '' })
const formError = ref('')

const handleSubmit = () => {
  const { name, email, message } = form
  if (!name || !email || !message) {
    formError.value = 'Please fill in all fields before sending.'
    return
  }
  formError.value = ''
  const waMessage = encodeURIComponent(`Hi Osemwegie! My name is ${name} (${email}).\n\n${message}`)
  window.open(`https://wa.me/2348157741603?text=${waMessage}`, '_blank')
  form.name = ''
  form.email = ''
  form.message = ''
}
</script>

<style scoped>
section {
  background: var(--navy);
  position: relative;
  overflow: hidden;
}

section::before {
  content: '';
  position: absolute;
  top: -150px; right: -150px;
  width: 500px; height: 500px;
  background: radial-gradient(circle, rgba(37,99,235,0.2) 0%, transparent 70%);
  border-radius: 50%;
  pointer-events: none;
}
.section-sub {
  font-weight: 500;
}

.contact-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: start;
  position: relative;
  z-index: 1;
}

.contact-left :deep(.section-tag) { color: var(--gold); }
.section-tag { color: var(--gold); display: inline-block; font-size: 1rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.75rem; }
.section-title { font-size: clamp(2.125rem, 3.5vw, 3rem); font-weight: 600; letter-spacing: -0.025em; color: var(--white); line-height: 1.15; margin-bottom: 1rem; }
.section-sub { font-size: 1.125rem; color: rgba(255,255,255,0.6); line-height: 1.7; max-width: 380px; }

.contact-methods {
  margin-top: 2.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  text-decoration: none;
}

.contact-method.static { cursor: default; }

.contact-icon {
  width: 44px; height: 44px;
  background: rgba(255,255,255,0.08);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  transition: background 0.2s, border-color 0.2s;
  color: rgba(255,255,255,0.7);
}

.contact-icon svg { width: 18px; height: 18px; }

.contact-method:not(.static):hover .contact-icon {
  background: rgba(255,255,255,0.14);
  border-color: rgba(255,255,255,0.22);
}

.wa-icon {
  background: rgba(37,211,102,0.15) !important;
  border-color: rgba(37,211,102,0.3) !important;
  color: var(--wa) !important;
}

.contact-method:hover .wa-icon {
  background: rgba(37,211,102,0.25) !important;
}

.cm-label {
  font-size: 1rem;
  color: rgba(255,255,255,0.4);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-bottom: 0.15rem;
}

.cm-value {
  font-size: 1.125rem;
  color: rgba(255,255,255,0.85);
  font-weight: 500;
}

.wa-value { color: var(--wa) !important; }

.contact-form {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 16px;
  padding: 2rem;
}

.form-row { margin-bottom: 1.25rem; }

.form-row label {
  display: block;
  font-size: 1rem;
  font-weight: 600;
  color: rgba(255,255,255,0.5);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-bottom: 0.5rem;
}

.form-row input,
.form-row textarea {
  width: 100%;
  background: rgba(255,255,255,0.07);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 8px;
  padding: 0.875rem 1.125rem;
  font-size: 1.0625rem;
  font-family: var(--font);
  color: var(--white);
  outline: none;
  transition: border-color 0.2s;
  resize: vertical;
}

.form-row input::placeholder,
.form-row textarea::placeholder { color: rgba(255,255,255,0.25); }

.form-row input:focus,
.form-row textarea:focus { border-color: rgba(37,99,235,0.6); }

.form-row textarea { min-height: 110px; }

.form-submit {
  width: 100%;
  background: var(--accent);
  color: var(--white);
  border: none;
  border-radius: 8px;
  padding: 1rem;
  font-size: 1.125rem;
  font-weight: 600;
  font-family: var(--font);
  cursor: pointer;
  transition: background 0.2s, transform 0.15s;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.form-submit:hover { background: #1d4ed8; transform: translateY(-1px); }

.form-error {
  font-size: 1rem;
  color: #f87171;
  margin-bottom: 0.75rem;
  padding: 0.625rem 0.875rem;
  background: rgba(248, 113, 113, 0.1);
  border: 1px solid rgba(248, 113, 113, 0.25);
  border-radius: 6px;
}

@media (max-width: 768px) {
  .contact-inner { grid-template-columns: 1fr; gap: 2.5rem; }
}
</style>
