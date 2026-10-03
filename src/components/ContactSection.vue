<script setup lang="ts">
import { ref } from 'vue'
import AppIcon from './AppIcon.vue'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const submitted = ref(false)
const loading = ref(false)

function handleSubmit() {
  loading.value = true
  setTimeout(() => {
    loading.value = false
    submitted.value = true
  }, 1000)
}

function handleReset() {
  form.value = {
    name: '',
    email: '',
    subject: '',
    message: '',
  }
  submitted.value = false
}
</script>

<template>
  <section id="contact" class="consultation-section">
    <!-- Top Half: Photo banner on left, Dot pattern on right -->
    <div class="consultation__top">
      <!-- Left Photo Background with Grayscale Business Meeting -->
      <div class="consultation__photo-bg">
        <img
          src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=1600&q=80"
          alt="Diverse corporate leadership team reviewing business strategy on laptop"
          class="consultation__img"
        />
        <div class="consultation__photo-overlay"></div>
      </div>

      <!-- Right Navy with Dot Pattern -->
      <div class="consultation__pattern-bg" aria-hidden="true"></div>
    </div>

    <!-- Main Content Container Overlapping Top & Bottom -->
    <div class="container consultation__container">
      <div class="consultation__grid">
        <!-- Left Column: Frosted Card + Contact Info Below -->
        <div class="consultation__left-col">
          <!-- Glassmorphism Card (Over the photo) -->
          <div class="consultation__glass-card">
            <p class="consultation__tag">NEED TECH CONSULTATION?</p>
            <h2 class="consultation__title">
              Ready to Modernize Your Stack?<br />
              Let’s Discuss Your Engineering Goals
            </h2>
          </div>

          <!-- Contact Details (In solid navy area) -->
          <div class="consultation__info-row">
            <!-- Address -->
            <div class="consultation__info-block">
              <span class="consultation__info-heading">Address</span>
              <div class="consultation__info-body">
                <div class="consultation__check-badge" aria-hidden="true">
                  <AppIcon name="check" :size="12" :stroke-width="2.8" />
                </div>
                <div class="consultation__info-text">
                  <p>1901 Thornridge Cir. Shiloh,</p>
                  <p>Hawaii 81063</p>
                </div>
              </div>
            </div>

            <!-- Vertical Divider -->
            <div class="consultation__info-sep" aria-hidden="true"></div>

            <!-- Contact -->
            <div class="consultation__info-block">
              <span class="consultation__info-heading">Contact</span>
              <div class="consultation__info-body">
                <div class="consultation__check-badge" aria-hidden="true">
                  <AppIcon name="check" :size="12" :stroke-width="2.8" />
                </div>
                <div class="consultation__info-text">
                  <a href="mailto:solutions@briamco.com">solutions@briamco.com</a>
                  <a href="tel:+6295550129">+629 555-0129</a>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Column: White Floating Form Card -->
        <div class="consultation__right-col">
          <div class="consultation__form-card">
            <!-- Form Success State -->
            <div v-if="submitted" class="consultation__form-success">
              <div class="consultation__success-icon">
                <AppIcon name="check-circle" :size="54" :stroke-width="1.8" />
              </div>
              <h3 class="consultation__form-title">Consultation Requested!</h3>
              <p class="consultation__success-desc">
                Thank you, <strong>{{ form.name || 'Valued Partner' }}</strong>. Our senior cloud architects and engineering directors will review your technical requirements and connect within 24 hours.
              </p>
              <button type="button" class="consultation__submit-pill" @click="handleReset">
                Send Another Request
              </button>
            </div>

            <!-- Normal Form State -->
            <div v-else>
              <h3 class="consultation__form-title">Schedule a Tech Architecture Call</h3>

              <!-- Features checklist row -->
              <div class="consultation__features">
                <span class="consultation__feature-item">
                  <span class="consultation__feature-check">✓</span> Principal Architects
                </span>
                <span class="consultation__feature-item">
                  <span class="consultation__feature-check">✓</span> Scalable Tech Roadmap
                </span>
                <span class="consultation__feature-item">
                  <span class="consultation__feature-check">✓</span> Rapid Delivery
                </span>
              </div>

              <!-- Form Inputs -->
              <form @submit.prevent="handleSubmit" class="consultation__form">
                <!-- Row 1: Name & Email -->
                <div class="consultation__form-row">
                  <div class="consultation__field">
                    <input
                      v-model="form.name"
                      type="text"
                      placeholder="Your Name"
                      required
                      class="consultation__input"
                    />
                  </div>
                  <div class="consultation__field">
                    <input
                      v-model="form.email"
                      type="email"
                      placeholder="Email"
                      required
                      class="consultation__input"
                    />
                  </div>
                </div>

                <!-- Row 2: Subject -->
                <div class="consultation__field">
                  <input
                    v-model="form.subject"
                    type="text"
                    placeholder="Subject"
                    required
                    class="consultation__input"
                  />
                </div>

                <!-- Row 3: Message -->
                <div class="consultation__field">
                  <textarea
                    v-model="form.message"
                    placeholder="Write a Message"
                    rows="4"
                    required
                    class="consultation__textarea"
                  ></textarea>
                </div>

                <!-- Action Button: Pill + Circle Arrow -->
                <div class="consultation__action">
                  <button
                    type="submit"
                    class="consultation__submit-pill"
                    :disabled="loading"
                  >
                    {{ loading ? 'Sending...' : 'Submit Request' }}
                  </button>
                  <button
                    type="submit"
                    class="consultation__submit-circle"
                    aria-label="Submit consultation request"
                    :disabled="loading"
                  >
                    <AppIcon name="arrow-up-right" :size="16" />
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom Decorative Multi-Stripes -->
    <div class="consultation__stripes" aria-hidden="true">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </section>
</template>

<style scoped>
/* ===== ROOT SECTION ===== */
.consultation-section {
  position: relative;
  background: #071426;
  color: #ffffff;
  overflow: hidden;
}

/* ===== TOP BACKGROUND AREA ===== */
.consultation__top {
  position: relative;
  height: 520px;
  width: 100%;
  display: flex;
}

/* Photo Background (Left ~72% of width) */
.consultation__photo-bg {
  position: relative;
  width: 72%;
  height: 100%;
  overflow: hidden;
}

.consultation__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 20%;
  filter: grayscale(88%) contrast(1.08) brightness(0.9);
  display: block;
}

.consultation__photo-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to right,
    rgba(7, 20, 38, 0.4) 0%,
    rgba(7, 20, 38, 0.2) 50%,
    rgba(7, 20, 38, 0.85) 90%,
    #071426 100%
  );
}

/* Pattern Background (Right ~28% of width) */
.consultation__pattern-bg {
  width: 28%;
  height: 100%;
  background-color: #071426;
  background-image: radial-gradient(rgba(255, 255, 255, 0.14) 1.5px, transparent 1.5px);
  background-size: 18px 18px;
}

/* ===== MAIN CONTAINER (OVERLAPS TOP & BOTTOM) ===== */
.consultation__container {
  position: relative;
  margin-top: -480px;
  padding-bottom: 96px;
  z-index: 10;
}

.consultation__grid {
  display: grid;
  grid-template-columns: 1.15fr 1fr;
  gap: 56px;
  align-items: start;
}

/* ===== LEFT COLUMN ===== */
.consultation__left-col {
  display: flex;
  flex-direction: column;
  padding-top: 240px;
}

/* Glassmorphism Frosted Card */
.consultation__glass-card {
  background: linear-gradient(
    135deg,
    rgba(255, 255, 255, 0.16) 0%,
    rgba(14, 27, 42, 0.65) 100%
  );
  backdrop-filter: blur(18px);
  -webkit-backdrop-filter: blur(18px);
  border: 1px solid rgba(255, 255, 255, 0.18);
  border-radius: 16px;
  padding: 38px 44px;
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.35);
  margin-bottom: 36px;
}

.consultation__tag {
  font-size: 11.5px;
  font-weight: 600;
  letter-spacing: 2.2px;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.72);
  margin-bottom: 16px;
}

.consultation__title {
  font-family: var(--font-display, 'Outfit', sans-serif);
  font-size: clamp(28px, 3vw, 40px);
  font-weight: 800;
  line-height: 1.18;
  color: #ffffff;
  letter-spacing: -0.8px;
}

/* Info Row (Address & Contact) */
.consultation__info-row {
  display: flex;
  align-items: center;
  gap: 32px;
  padding-left: 8px;
}

.consultation__info-block {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.consultation__info-heading {
  font-size: 13.5px;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.9);
  letter-spacing: 0.2px;
}

.consultation__info-body {
  display: flex;
  align-items: flex-start;
  gap: 12px;
}

.consultation__check-badge {
  width: 26px;
  height: 26px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #ffffff;
  flex-shrink: 0;
  margin-top: 2px;
}

.consultation__info-text {
  font-size: 13.5px;
  color: rgba(255, 255, 255, 0.72);
  line-height: 1.55;
  display: flex;
  flex-direction: column;
}

.consultation__info-text a {
  color: rgba(255, 255, 255, 0.72);
  text-decoration: none;
  transition: color 0.2s;
}

.consultation__info-text a:hover {
  color: #ffffff;
}

.consultation__info-sep {
  width: 1px;
  height: 52px;
  background: rgba(255, 255, 255, 0.14);
  flex-shrink: 0;
}

/* ===== RIGHT COLUMN: FORM CARD ===== */
.consultation__right-col {
  width: 100%;
  padding-top: 100px;
}

.consultation__form-card {
  background: #ffffff;
  color: #0e1b2a;
  border-radius: 14px;
  padding: 44px 40px;
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.35);
  border: 1px solid rgba(255, 255, 255, 0.08);
}

.consultation__form-title {
  font-family: var(--font-display, 'Outfit', sans-serif);
  font-size: 24px;
  font-weight: 700;
  color: #0e1b2a;
  text-align: center;
  letter-spacing: -0.4px;
  margin-bottom: 12px;
}

/* Features checklist row */
.consultation__features {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-bottom: 28px;
}

.consultation__feature-item {
  font-size: 12.5px;
  font-weight: 500;
  color: #374151;
  display: inline-flex;
  align-items: center;
  gap: 5px;
}

.consultation__feature-check {
  font-size: 13px;
  font-weight: 700;
  color: #111827;
}

/* Form inputs */
.consultation__form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.consultation__form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
}

.consultation__field {
  width: 100%;
}

.consultation__input,
.consultation__textarea {
  width: 100%;
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  padding: 13px 16px;
  font-size: 13.5px;
  font-family: var(--font-main, 'Inter', sans-serif);
  color: #111827;
  background: #ffffff;
  transition: all 0.2s ease;
}

.consultation__input::placeholder,
.consultation__textarea::placeholder {
  color: #6b7280;
  font-size: 13px;
}

.consultation__input:focus,
.consultation__textarea:focus {
  outline: none;
  border-color: #0e1b2a;
  box-shadow: 0 0 0 3px rgba(14, 27, 42, 0.08);
}

.consultation__textarea {
  min-height: 125px;
  resize: vertical;
}

/* Action button pair */
.consultation__action {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin-top: 8px;
}

.consultation__submit-pill {
  display: inline-flex;
  align-items: center;
  background: #0e1b2a;
  color: #ffffff;
  padding: 13px 28px;
  border-radius: 99px;
  font-size: 13.5px;
  font-weight: 600;
  border: none;
  cursor: pointer;
  letter-spacing: 0.2px;
  transition: all 0.25s ease;
  font-family: inherit;
}

.consultation__submit-pill:hover:not(:disabled) {
  background: #1e3a5f;
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(14, 27, 42, 0.25);
}

.consultation__submit-pill:disabled {
  opacity: 0.65;
  cursor: not-allowed;
}

.consultation__submit-circle {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 1px solid #0e1b2a;
  background: transparent;
  color: #0e1b2a;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.25s ease;
  flex-shrink: 0;
}

.consultation__submit-circle:hover:not(:disabled) {
  background: #0e1b2a;
  color: #ffffff;
  transform: translateY(-1px);
}

.consultation__submit-circle:disabled {
  opacity: 0.65;
  cursor: not-allowed;
}

/* Form Success State */
.consultation__form-success {
  text-align: center;
  padding: 24px 8px;
}

.consultation__success-icon {
  color: #10b981;
  display: flex;
  justify-content: center;
  margin-bottom: 16px;
}

.consultation__success-desc {
  font-size: 14px;
  color: #4b5563;
  line-height: 1.6;
  margin: 12px 0 24px;
}

/* ===== BOTTOM STRIPES ===== */
.consultation__stripes {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 3px;
  padding: 8px 0;
  background: #050d18;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.consultation__stripes span {
  display: block;
  width: 100%;
  height: 1px;
  background: rgba(255, 255, 255, 0.12);
}

/* ===== RESPONSIVE ===== */
@media (max-width: 1024px) {
  .consultation__grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .consultation__container {
    margin-top: -240px;
  }

  .consultation__photo-bg {
    width: 100%;
  }

  .consultation__pattern-bg {
    display: none;
  }
}

@media (max-width: 640px) {
  .consultation__top {
    height: 320px;
  }

  .consultation__container {
    margin-top: -180px;
  }

  .consultation__glass-card {
    padding: 28px 24px;
    margin-bottom: 32px;
  }

  .consultation__info-row {
    flex-direction: column;
    align-items: flex-start;
    gap: 20px;
  }

  .consultation__info-sep {
    display: none;
  }

  .consultation__form-card {
    padding: 32px 20px;
  }

  .consultation__form-row {
    grid-template-columns: 1fr;
  }
}
</style>
