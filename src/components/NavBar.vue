<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import AppIcon from './AppIcon.vue'

const scrolled = ref(false)
const mobileMenuOpen = ref(false)
const currentLang = ref<'EN' | 'ID'>('EN')

function toggleLang() {
  currentLang.value = currentLang.value === 'EN' ? 'ID' : 'EN'
}

function setLang(lang: 'EN' | 'ID') {
  currentLang.value = lang
}

const navLinks = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Services', href: '#services' },
  { label: 'Solutions', href: '#solutions' },
  { label: 'Testimonials', href: '#testimonials' },
  { label: 'Blog', href: '#blog' },
  { label: 'Contact', href: '#contact' },
]

function handleScroll() {
  scrolled.value = window.scrollY > 60
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <nav class="navbar" :class="{ 'navbar--scrolled': scrolled }">
    <div class="navbar__inner">
      <a href="#home" class="navbar__logo">
        <img src="/logo.svg" alt="BRIAMCO Logo" class="navbar__logo-img" />
      </a>

      <ul class="navbar__links">
        <li v-for="link in navLinks" :key="link.label">
          <a :href="link.href" class="navbar__link">{{ link.label }}</a>
        </li>
      </ul>

      <div class="navbar__actions">
        <!-- Language Switcher Pill -->
        <div class="navbar__lang-switch">
          <div
            class="lang-pill"
            @click="toggleLang"
            :title="'Current: ' + currentLang + ' (Click to switch)'"
          >
            <AppIcon name="globe" :size="15" />
            <button
              type="button"
              class="lang-btn"
              :class="{ 'lang-btn--active': currentLang === 'EN' }"
              @click.stop="setLang('EN')"
              aria-label="Switch to English"
            >
              EN
            </button>
            <span class="lang-divider">/</span>
            <button
              type="button"
              class="lang-btn"
              :class="{ 'lang-btn--active': currentLang === 'ID' }"
              @click.stop="setLang('ID')"
              aria-label="Ganti ke Bahasa Indonesia"
            >
              ID
            </button>
          </div>
        </div>

        <button
          class="navbar__burger"
          :class="{ open: mobileMenuOpen }"
          @click="mobileMenuOpen = !mobileMenuOpen"
          aria-label="Toggle menu"
        >
          <span></span><span></span><span></span>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div class="navbar__mobile" :class="{ 'navbar__mobile--open': mobileMenuOpen }">
      <ul>
        <li v-for="link in navLinks" :key="link.label">
          <a :href="link.href" class="navbar__mobile-link" @click="mobileMenuOpen = false">{{ link.label }}</a>
        </li>
      </ul>
      <div class="navbar__mobile-lang">
        <div class="lang-pill lang-pill--mobile">
          <AppIcon name="globe" :size="16" />
          <button
            type="button"
            class="lang-btn"
            :class="{ 'lang-btn--active': currentLang === 'EN' }"
            @click="setLang('EN')"
          >
            English (EN)
          </button>
          <span class="lang-divider">|</span>
          <button
            type="button"
            class="lang-btn"
            :class="{ 'lang-btn--active': currentLang === 'ID' }"
            @click="setLang('ID')"
          >
            Bahasa (ID)
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
/* ===== FLOATING NAVBAR ===== */
.navbar {
  position: fixed;
  top: calc(36px + 12px); /* topbar height + gap */
  left: 50%;
  transform: translateX(-50%);
  width: calc(100% - 48px);
  max-width: 1200px;
  z-index: 999;
  border-radius: 14px;
  padding: 0;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  background: rgba(13, 27, 42, 0.55);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.25);
}

.navbar--scrolled {
  top: 10px;
  background: rgba(13, 27, 42, 0.92);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  border-color: rgba(255, 255, 255, 0.08);
  box-shadow: 0 16px 48px rgba(0, 0, 0, 0.4);
}

/* ===== INNER ===== */
.navbar__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  padding: 14px 28px;
}

/* ===== LOGO ===== */
.navbar__logo {
  flex-shrink: 0;
  display: flex;
  align-items: center;
}

.navbar__logo-img {
  height: 28px;
  width: auto;
  /* SVG já é branco, sem filtro necessário */
}

/* ===== LINKS ===== */
.navbar__links {
  display: flex;
  align-items: center;
  gap: 2px;
  flex: 1;
  justify-content: center;
}

.navbar__link {
  font-size: 13.5px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.75);
  padding: 7px 14px;
  border-radius: 8px;
  transition: all 0.22s;
  letter-spacing: 0.2px;
}

.navbar__link:hover {
  color: #fff;
  background: rgba(255, 255, 255, 0.1);
}

/* ===== ACTIONS ===== */
.navbar__actions {
  display: flex;
  align-items: center;
  gap: 12px;
  flex-shrink: 0;
}

/* ===== LANGUAGE SWITCHER ===== */
.navbar__lang-switch {
  display: flex;
  align-items: center;
}

.lang-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.16);
  padding: 6px 14px;
  border-radius: 99px;
  color: #ffffff;
  transition: all 0.25s ease;
  user-select: none;
  cursor: pointer;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
}

.lang-pill:hover {
  background: rgba(255, 255, 255, 0.14);
  border-color: rgba(255, 255, 255, 0.28);
  transform: translateY(-1px);
}

.lang-btn {
  background: none;
  border: none;
  padding: 0;
  font-family: inherit;
  font-size: 13px;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.55);
  cursor: pointer;
  transition: all 0.2s ease;
  letter-spacing: 0.5px;
}

.lang-btn:hover {
  color: rgba(255, 255, 255, 0.9);
}

.lang-btn--active {
  color: #ffffff;
  font-weight: 700;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
}

.lang-divider {
  color: rgba(255, 255, 255, 0.3);
  font-size: 12px;
  user-select: none;
}

/* ===== BURGER ===== */
.navbar__burger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.navbar__burger span {
  display: block;
  width: 22px;
  height: 2px;
  background: white;
  border-radius: 2px;
  transition: all 0.3s;
}

.navbar__burger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.navbar__burger.open span:nth-child(2) { opacity: 0; transform: scaleX(0); }
.navbar__burger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* ===== MOBILE MENU ===== */
.navbar__mobile {
  display: none;
  background: rgba(10, 21, 32, 0.98);
  border-top: 1px solid rgba(255, 255, 255, 0.07);
  border-radius: 0 0 14px 14px;
  overflow: hidden;
  max-height: 0;
  transition: max-height 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.navbar__mobile--open {
  max-height: 420px;
}

.navbar__mobile ul {
  padding: 8px 24px;
}

.navbar__mobile li {
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
}

.navbar__mobile-link {
  display: block;
  color: rgba(255, 255, 255, 0.8);
  font-size: 15px;
  font-weight: 500;
  padding: 13px 0;
  transition: color 0.2s;
}

.navbar__mobile-link:hover { color: white; }

/* Mobile language switcher */
.navbar__mobile-lang {
  padding: 16px 24px 22px;
  display: flex;
  justify-content: center;
}

.lang-pill--mobile {
  padding: 10px 22px;
  font-size: 14px;
  gap: 12px;
  background: rgba(255, 255, 255, 0.07);
  border: 1px solid rgba(255, 255, 255, 0.15);
}

.lang-pill--mobile .lang-btn {
  font-size: 14px;
}

/* ===== RESPONSIVE ===== */
@media (max-width: 900px) {
  .navbar__links { display: none; }
  .navbar__lang-switch { display: none; }
  .navbar__burger { display: flex; }
  .navbar__mobile { display: block; }
}

@media (max-width: 600px) {
  .navbar {
    width: calc(100% - 24px);
    top: calc(36px + 8px);
    border-radius: 10px;
  }

  .navbar--scrolled {
    top: 6px;
  }

  .navbar__inner {
    padding: 12px 18px;
  }
}
</style>
