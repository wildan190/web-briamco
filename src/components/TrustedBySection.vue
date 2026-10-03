<script setup lang="ts">
// Trusted By section with partner/client brand logos
</script>

<template>
  <section class="trusted-section">
    <div class="container">
      <!-- Centered Header with Left & Right Dividing Lines -->
      <div class="trusted__header">
        <span class="trusted__line" aria-hidden="true"></span>
        <p class="trusted__title">
          Trusted by <strong>1200+</strong> founders &amp; business owners
        </p>
        <span class="trusted__line" aria-hidden="true"></span>
      </div>

      <!-- Logos Row: 6 Brands -->
      <div class="trusted__logos">
        <!-- 1. MARKETING / AGENCY SLOGAN -->
        <div class="trusted__logo-item" title="Marketing Agency">
          <svg width="155" height="42" viewBox="0 0 160 44" fill="none" class="trusted__svg trusted__svg--muted">
            <!-- Icon -->
            <path d="M14 6L4 26H11L14 19H22L25 26H32L22 6H14ZM16.5 13.5L18 9.8L19.5 13.5H16.5Z" fill="currentColor"/>
            <path d="M12 28L4 38H11L13 33.5H23L25 38H32L24 28H12Z" fill="currentColor" fill-opacity="0.8"/>
            <!-- Text -->
            <text x="38" y="22" font-family="'Inter', sans-serif" font-size="14.5" font-weight="800" fill="currentColor" letter-spacing="1">MARKETING</text>
            <text x="39" y="34" font-family="'Inter', sans-serif" font-size="8.5" font-weight="600" fill="currentColor" fill-opacity="0.75" letter-spacing="1.8">AGENCY SLOGAN</text>
          </svg>
        </div>

        <!-- 2. Carriest / SLOGAN HERE -->
        <div class="trusted__logo-item" title="Carriest">
          <svg width="145" height="42" viewBox="0 0 150 44" fill="none" class="trusted__svg trusted__svg--muted">
            <!-- Compass/Target Icon -->
            <circle cx="16" cy="22" r="11" stroke="currentColor" stroke-width="2.5"/>
            <circle cx="16" cy="22" r="4.5" fill="currentColor"/>
            <path d="M16 35L12.5 30H19.5L16 35Z" fill="currentColor"/>
            <!-- Text -->
            <text x="36" y="24" font-family="'Georgia', serif" font-size="18.5" font-weight="700" fill="currentColor" letter-spacing="-0.3">Carriest</text>
            <text x="37" y="35" font-family="'Inter', sans-serif" font-size="8" font-weight="600" fill="currentColor" fill-opacity="0.75" letter-spacing="2.2">SLOGAN HERE</text>
          </svg>
        </div>

        <!-- 3. Alohu / THE GAME (High contrast / dark) -->
        <div class="trusted__logo-item" title="Alohu">
          <svg width="135" height="42" viewBox="0 0 140 44" fill="none" class="trusted__svg trusted__svg--dark">
            <!-- Bold Stylized 'A' -->
            <path d="M15 6L4 36H11.5L15 26.5H24L26 31.5H19L17.5 36H32L21 6H15Z" fill="currentColor"/>
            <circle cx="12" cy="30" r="2.5" fill="currentColor"/>
            <circle cx="27" cy="23" r="2.2" fill="currentColor"/>
            <line x1="12" y1="30" x2="27" y2="23" stroke="currentColor" stroke-width="1.8"/>
            <!-- Text -->
            <text x="38" y="24" font-family="'Outfit', sans-serif" font-size="22" font-weight="800" fill="currentColor" letter-spacing="-0.5">Alohu</text>
            <text x="39" y="36" font-family="'Inter', sans-serif" font-size="9" font-weight="800" fill="currentColor" letter-spacing="3.8">THE GAME</text>
          </svg>
        </div>

        <!-- 4. Minest / AUTOMATION -->
        <div class="trusted__logo-item" title="Minest">
          <svg width="140" height="42" viewBox="0 0 145 44" fill="none" class="trusted__svg trusted__svg--muted">
            <!-- Modern Ribbon / Wave Icon -->
            <path d="M12 9C7.5 9 4 12.8 4 17.5C4 23 8.5 27 13.5 27C17 27 19.5 25 21 22.5L25 29C22.5 32.5 18 35 13 35C5.5 35 0 29 0 21C0 12 6.5 5 15 5C19 5 22.5 6.5 25 9.5L20.5 14C19 12 16.5 10.5 13.5 10.5L12 9Z" fill="currentColor" transform="translate(4, 0) scale(0.9)"/>
            <!-- Text -->
            <text x="38" y="23" font-family="'Inter', sans-serif" font-size="18.5" font-weight="700" fill="currentColor" letter-spacing="-0.3">Minest</text>
            <text x="39" y="34" font-family="'Inter', sans-serif" font-size="8.5" font-weight="600" fill="currentColor" fill-opacity="0.75" letter-spacing="2.4">AUTOMATION</text>
          </svg>
        </div>

        <!-- 5. Success / GOOD PEOPLE -->
        <div class="trusted__logo-item" title="Success">
          <svg width="150" height="42" viewBox="0 0 155 44" fill="none" class="trusted__svg trusted__svg--muted">
            <!-- Rounded card with person & star -->
            <rect x="4" y="9" width="24" height="24" rx="6" fill="currentColor" fill-opacity="0.85"/>
            <circle cx="16" cy="18" r="3" fill="#ffffff"/>
            <path d="M10 28C10.5 24 13.5 22.5 16 22.5C18.5 22.5 21.5 24 22 28H10Z" fill="#ffffff"/>
            <path d="M25 8L26 11L29 12L26 13L25 16L24 13L21 12L24 11L25 8Z" fill="currentColor"/>
            <!-- Text -->
            <text x="38" y="24" font-family="'Outfit', sans-serif" font-size="18.5" font-weight="800" fill="currentColor" letter-spacing="-0.3">Success</text>
            <text x="39" y="35" font-family="'Inter', sans-serif" font-size="8.5" font-weight="600" fill="currentColor" fill-opacity="0.75" letter-spacing="2.2">GOOD PEOPLE</text>
          </svg>
        </div>

        <!-- 6. Minest / AUTOMATION (Second instance as in reference) -->
        <div class="trusted__logo-item" title="Minest">
          <svg width="140" height="42" viewBox="0 0 145 44" fill="none" class="trusted__svg trusted__svg--muted">
            <!-- Modern Ribbon / Wave Icon -->
            <path d="M12 9C7.5 9 4 12.8 4 17.5C4 23 8.5 27 13.5 27C17 27 19.5 25 21 22.5L25 29C22.5 32.5 18 35 13 35C5.5 35 0 29 0 21C0 12 6.5 5 15 5C19 5 22.5 6.5 25 9.5L20.5 14C19 12 16.5 10.5 13.5 10.5L12 9Z" fill="currentColor" transform="translate(4, 0) scale(0.9)"/>
            <!-- Text -->
            <text x="38" y="23" font-family="'Inter', sans-serif" font-size="18.5" font-weight="700" fill="currentColor" letter-spacing="-0.3">Minest</text>
            <text x="39" y="34" font-family="'Inter', sans-serif" font-size="8.5" font-weight="600" fill="currentColor" fill-opacity="0.75" letter-spacing="2.4">AUTOMATION</text>
          </svg>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* ===== TRUSTED BY SECTION ===== */
.trusted-section {
  background: #ffffff;
  padding: 64px 0 76px;
  position: relative;
  border-top: 1px solid #f1f5f9;
}

/* Header line */
.trusted__header {
  display: flex;
  align-items: center;
  gap: 28px;
  margin-bottom: 52px;
  width: 100%;
}

.trusted__line {
  flex: 1;
  height: 1px;
  background: #e5e7eb;
}

.trusted__title {
  font-size: 13.5px;
  color: #64748b;
  white-space: nowrap;
  letter-spacing: 0.2px;
  text-align: center;
}

.trusted__title strong {
  color: #0f172a;
  font-weight: 700;
}

/* Logos Row */
.trusted__logos {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 36px;
  width: 100%;
}

.trusted__logo-item {
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer;
  flex-shrink: 0;
}

.trusted__logo-item:hover {
  transform: translateY(-2px);
}

.trusted__svg {
  display: block;
  transition: all 0.25s ease;
}

/* Muted grey logos */
.trusted__svg--muted {
  color: #94a3b8;
  opacity: 0.85;
}

.trusted__logo-item:hover .trusted__svg--muted {
  color: #64748b;
  opacity: 1;
}

/* High contrast dark logo (Alohu) */
.trusted__svg--dark {
  color: #0e1b2a;
  opacity: 1;
}

.trusted__logo-item:hover .trusted__svg--dark {
  color: #1d4ed8;
}

/* ===== RESPONSIVE ===== */
@media (max-width: 1080px) {
  .trusted__logos {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 36px 24px;
    justify-items: center;
  }
}

@media (max-width: 640px) {
  .trusted-section {
    padding: 48px 0 56px;
  }

  .trusted__header {
    gap: 16px;
    margin-bottom: 36px;
  }

  .trusted__title {
    font-size: 12px;
    white-space: normal;
  }

  .trusted__logos {
    grid-template-columns: repeat(2, 1fr);
    gap: 28px 16px;
  }
}
</style>
