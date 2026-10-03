<script setup lang="ts">
const footerLinks = {
  Solutions: ['Cloud Architecture', 'DevOps & CI/CD', 'Custom Software', 'AI & Data Intelligence', 'Cybersecurity'],
  Company: ['About Us', 'Engineering Team', 'Case Studies', 'Tech Insights', 'Careers'],
  Developers: ['API Documentation', 'System Status', 'Open Source', 'Security Whitepapers', 'Contact Engineering'],
}
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__top">
        <!-- Brand -->
        <div class="footer__brand">
          <a href="#home" class="footer__logo">
            <img src="/logo.svg" alt="BRIAMCO Logo" />
          </a>
          <p class="footer__tagline">
            Empowering enterprises through modern cloud architectures, scalable software engineering, and intelligent AI systems.
          </p>
          <div class="footer__socials">
            <a href="#" class="footer__social" aria-label="LinkedIn">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
            <a href="#" class="footer__social" aria-label="Twitter/X">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
            </a>
            <a href="#" class="footer__social" aria-label="Instagram">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
            </a>
          </div>
        </div>

        <!-- Links -->
        <div v-for="(links, category) in footerLinks" :key="category" class="footer__col">
          <h4 class="footer__col-title">{{ category }}</h4>
          <ul class="footer__col-list">
            <li v-for="link in links" :key="link">
              <a href="#" class="footer__col-link">{{ link }}</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="footer__bottom">
        <p class="footer__copy">© {{ new Date().getFullYear() }} BRIAMCO. All rights reserved.</p>
        <div class="footer__legal">
          <a href="#" class="footer__legal-link">Privacy Policy</a>
          <a href="#" class="footer__legal-link">Terms of Service</a>
          <a href="#" class="footer__legal-link">Cookie Policy</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--navy);
  padding: 80px 0 0;
  color: rgba(255,255,255,0.7);
}

.footer__top {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 48px;
  margin-bottom: 60px;
}

.footer__logo {
  display: inline-block;
  margin-bottom: 16px;
}

.footer__logo img {
  height: 28px;
  width: auto;
}

.footer__tagline {
  font-size: 14px;
  line-height: 1.7;
  color: rgba(255,255,255,0.55);
  margin-bottom: 24px;
  max-width: 280px;
}

.footer__socials {
  display: flex;
  gap: 10px;
}

.footer__social {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: rgba(255,255,255,0.08);
  color: rgba(255,255,255,0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.25s;
}

.footer__social:hover {
  background: var(--accent);
  color: white;
  transform: translateY(-3px);
}

.footer__col-title {
  font-size: 13px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: white;
  margin-bottom: 20px;
}

.footer__col-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.footer__col-link {
  font-size: 14px;
  color: rgba(255,255,255,0.55);
  transition: color 0.2s;
}

.footer__col-link:hover {
  color: white;
}

.footer__bottom {
  border-top: 1px solid rgba(255,255,255,0.08);
  padding: 24px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
}

.footer__copy {
  font-size: 13px;
  color: rgba(255,255,255,0.4);
}

.footer__legal {
  display: flex;
  gap: 24px;
}

.footer__legal-link {
  font-size: 13px;
  color: rgba(255,255,255,0.4);
  transition: color 0.2s;
}

.footer__legal-link:hover { color: white; }

@media (max-width: 900px) {
  .footer__top { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 580px) {
  .footer__top { grid-template-columns: 1fr; }
  .footer__bottom { flex-direction: column; align-items: flex-start; }
}
</style>
