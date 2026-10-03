<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import AboutSection from './components/AboutSection.vue'
import SolutionsSection from './components/SolutionsSection.vue'
import CtaBanner from './components/CtaBanner.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import TeamSection from './components/TeamSection.vue'
import FaqSection from './components/FaqSection.vue'
import BlogSection from './components/BlogSection.vue'
import ContactSection from './components/ContactSection.vue'
import TrustedBySection from './components/TrustedBySection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div id="app-root">
    <NavBar />
    <main>
      <HeroSection />
      <ServicesSection />
      <AboutSection />
      <SolutionsSection />
      <CtaBanner />
      <TestimonialsSection />
      <TeamSection />
      <FaqSection />
      <BlogSection />
      <ContactSection />
      <TrustedBySection />
    </main>
    <FooterSection />
  </div>
</template>

<style>
@import './assets/main.css';

#app-root {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
}
</style>
