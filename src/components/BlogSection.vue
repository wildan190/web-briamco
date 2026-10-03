<script setup lang="ts">
import AppIcon from './AppIcon.vue'

interface Article {
  id: number
  badge: string
  author: string
  title: string
  excerpt: string
  day: string
  month: string
  img: string
  alt: string
}

const articles: Article[] = [
  {
    id: 1,
    badge: 'Cloud Architecture',
    author: 'Post By Architecture Lead',
    title: 'Migrating Monoliths to Event-Driven Microservices at Enterprise Scale',
    excerpt: 'Key strategies, patterns, and pitfall prevention for transitioning mission-critical transactional systems without customer downtime.',
    day: '18',
    month: 'Sept',
    img: 'https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=700&q=80',
    alt: 'Software engineers reviewing cloud architecture diagrams',
  },
  {
    id: 2,
    badge: 'AI & Data Engineering',
    author: 'Post By AI Research Team',
    title: 'Deploying Production-Grade Enterprise RAG & Secure LLM Pipelines',
    excerpt: 'How modern engineering teams manage private vector databases, reduce hallucinations, and enforce strict token privacy guardrails.',
    day: '24',
    month: 'Sept',
    img: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&w=700&q=80',
    alt: 'Data scientists discussing machine learning pipeline benchmarks',
  },
]
</script>

<template>
  <section id="blog" class="blog-section">
    <div class="container">
      <div class="blog-grid">
        <!-- Left Column: Heading & CTA -->
        <div class="blog__intro">
          <p class="blog__label">TECH INSIGHTS &amp; ENGINEERING</p>
          <h2 class="blog__headline">
            Check Out Latest<br />Tech Updates &amp;<br />Articles
          </h2>

          <div class="blog__divider" aria-hidden="true"></div>

          <p class="blog__desc">
            Stay ahead of the curve with deep architectural insights, cloud benchmarks, and enterprise engineering practices.
          </p>

          <div class="blog__cta-group">
            <a href="#blog" class="blog__cta-pill">See All Blog</a>
            <a href="#blog" class="blog__cta-circle" aria-label="See all blog posts">
              <AppIcon name="arrow-up-right" :size="17" />
            </a>
          </div>
        </div>

        <!-- Right Column: 2 Blog Cards Stacked -->
        <div class="blog__list">
          <article
            v-for="post in articles"
            :key="post.id"
            class="blog-card"
          >
            <!-- Thumbnail with Date Badge -->
            <div class="blog-card__thumb">
              <img
                :src="post.img"
                :alt="post.alt"
                loading="lazy"
                class="blog-card__img"
              />
              <div class="blog-card__thumb-bg" aria-hidden="true"></div>
              <div class="blog-card__date">
                <span class="blog-card__date-day">{{ post.day }}</span>
                <span class="blog-card__date-month">{{ post.month }}</span>
              </div>
            </div>

            <!-- Content Area -->
            <div class="blog-card__content">
              <!-- Meta: Badge + Author -->
              <div class="blog-card__meta">
                <span class="blog-card__badge">{{ post.badge }}</span>
                <span class="blog-card__author">{{ post.author }}</span>
              </div>

              <!-- Title -->
              <h3 class="blog-card__title">
                <a href="#blog">{{ post.title }}</a>
              </h3>

              <!-- Subtle Divider Line -->
              <div class="blog-card__line" aria-hidden="true"></div>

              <!-- Excerpt -->
              <p class="blog-card__excerpt">{{ post.excerpt }}</p>

              <!-- Read More Button + Arrow Circle -->
              <div class="blog-card__action">
                <a href="#blog" class="blog-card__btn-pill">Read More</a>
                <a href="#blog" class="blog-card__btn-circle" aria-label="Read article">
                  <AppIcon name="arrow-up-right" :size="15" />
                </a>
              </div>
            </div>
          </article>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* ===== BLOG SECTION ===== */
.blog-section {
  background: #ffffff;
  padding: 100px 0 110px;
  position: relative;
}

.blog-grid {
  display: grid;
  grid-template-columns: 360px 1fr;
  gap: 72px;
  align-items: start;
}

/* ===== LEFT INTRO ===== */
.blog__intro {
  display: flex;
  flex-direction: column;
}

.blog__label {
  font-size: 11.5px;
  font-weight: 600;
  letter-spacing: 2.2px;
  text-transform: uppercase;
  color: #64748b;
  margin-bottom: 16px;
}

.blog__headline {
  font-family: var(--font-display, 'Outfit', sans-serif);
  font-size: clamp(32px, 3.4vw, 44px);
  font-weight: 800;
  color: #0e1b2a;
  line-height: 1.14;
  letter-spacing: -1.2px;
}

.blog__divider {
  width: 100%;
  max-width: 320px;
  height: 1px;
  background: #e2e8f0;
  margin: 36px 0 24px;
}

.blog__desc {
  font-size: 14.5px;
  color: #64748b;
  line-height: 1.65;
  max-width: 310px;
  margin-bottom: 28px;
}

/* CTA Buttons (Pill + Circle) */
.blog__cta-group {
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.blog__cta-pill {
  display: inline-flex;
  align-items: center;
  background: #0e1b2a;
  color: #ffffff;
  padding: 13px 26px;
  border-radius: 99px;
  font-size: 13.5px;
  font-weight: 600;
  letter-spacing: 0.2px;
  text-decoration: none;
  transition: all 0.25s ease;
}

.blog__cta-pill:hover {
  background: #1e3a5f;
  transform: translateY(-1px);
  box-shadow: 0 6px 20px rgba(14, 27, 42, 0.22);
}

.blog__cta-circle {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 1px solid #0e1b2a;
  background: transparent;
  color: #0e1b2a;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: all 0.25s ease;
  flex-shrink: 0;
}

.blog__cta-circle:hover {
  background: #0e1b2a;
  color: #ffffff;
  transform: translateY(-1px);
}

/* ===== RIGHT BLOG LIST ===== */
.blog__list {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

/* Card */
.blog-card {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 32px;
  align-items: center;
}

/* Card Thumbnail */
.blog-card__thumb {
  position: relative;
  width: 100%;
  height: 205px;
  border-radius: 14px;
  overflow: hidden;
  background: linear-gradient(135deg, #1e3a5f 0%, #0e1b2a 100%);
  flex-shrink: 0;
}

.blog-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.4s ease;
}

.blog-card:hover .blog-card__img {
  transform: scale(1.04);
}

.blog-card__thumb-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(14, 27, 42, 0.28) 0%, transparent 60%);
  pointer-events: none;
}

/* Date Badge */
.blog-card__date {
  position: absolute;
  bottom: 12px;
  right: 12px;
  min-width: 52px;
  padding: 6px 12px;
  background: rgba(14, 27, 42, 0.72);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: 8px;
  color: #ffffff;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  border: 1px solid rgba(255, 255, 255, 0.12);
}

.blog-card__date-day {
  font-size: 18px;
  font-weight: 700;
  line-height: 1;
  letter-spacing: -0.5px;
}

.blog-card__date-month {
  font-size: 11px;
  font-weight: 500;
  opacity: 0.9;
  margin-top: 3px;
  text-transform: capitalize;
}

/* Card Content */
.blog-card__content {
  display: flex;
  flex-direction: column;
}

/* Meta */
.blog-card__meta {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 12px;
}

.blog-card__badge {
  background: #f1f5f9;
  color: #475569;
  font-size: 11.5px;
  font-weight: 600;
  padding: 4px 12px;
  border-radius: 4px;
  letter-spacing: 0.2px;
}

.blog-card__author {
  font-size: 13px;
  color: #64748b;
  font-weight: 500;
}

/* Title */
.blog-card__title {
  font-family: var(--font-display, 'Outfit', sans-serif);
  font-size: 19px;
  font-weight: 700;
  line-height: 1.35;
  color: #0e1b2a;
  letter-spacing: -0.3px;
}

.blog-card__title a {
  color: inherit;
  text-decoration: none;
  transition: color 0.2s ease;
}

.blog-card__title a:hover {
  color: var(--accent, #2563eb);
}

/* Line Divider */
.blog-card__line {
  width: 100%;
  height: 1px;
  background: #f1f5f9;
  margin: 14px 0 13px;
}

/* Excerpt */
.blog-card__excerpt {
  font-size: 13.5px;
  color: #64748b;
  line-height: 1.62;
  margin-bottom: 16px;
}

/* Read More Action */
.blog-card__action {
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.blog-card__btn-pill {
  display: inline-flex;
  align-items: center;
  background: #0e1b2a;
  color: #ffffff;
  padding: 9px 20px;
  border-radius: 99px;
  font-size: 12.5px;
  font-weight: 600;
  letter-spacing: 0.2px;
  text-decoration: none;
  transition: all 0.25s ease;
}

.blog-card__btn-pill:hover {
  background: #1e3a5f;
  transform: translateY(-1px);
  box-shadow: 0 4px 14px rgba(14, 27, 42, 0.2);
}

.blog-card__btn-circle {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: 1px solid #0e1b2a;
  background: transparent;
  color: #0e1b2a;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: all 0.25s ease;
  flex-shrink: 0;
}

.blog-card__btn-circle:hover {
  background: #0e1b2a;
  color: #ffffff;
  transform: translateY(-1px);
}

/* ===== RESPONSIVE ===== */
@media (max-width: 1024px) {
  .blog-grid {
    grid-template-columns: 300px 1fr;
    gap: 48px;
  }

  .blog-card {
    grid-template-columns: 240px 1fr;
    gap: 24px;
  }

  .blog-card__thumb {
    height: 185px;
  }
}

@media (max-width: 860px) {
  .blog-section {
    padding: 72px 0 80px;
  }

  .blog-grid {
    grid-template-columns: 1fr;
    gap: 48px;
  }

  .blog__headline br {
    display: none;
  }

  .blog__divider {
    margin: 24px 0 16px;
  }
}

@media (max-width: 600px) {
  .blog-card {
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .blog-card__thumb {
    height: 210px;
  }
}
</style>
