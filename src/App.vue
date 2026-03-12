<script setup>
import { onMounted } from 'vue'

import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

import HeroSection from './sections/HeroSection.vue'
import AboutSection from './sections/AboutSection.vue'
import HistorySection from './sections/HistorySection.vue'
import VisionSection from './sections/VisionSection.vue'
import ProductSection from './sections/ProductSection.vue'
import ContactSection from './sections/ContactSection.vue'

onMounted(() => {
  const targets = document.querySelectorAll('.reveal')

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show')
        } else {
          entry.target.classList.remove('show')
        }
      })
    },
    {
      threshold: 0.18,
      rootMargin: '0px 0px -10% 0px'
    }
  )

  targets.forEach((target) => observer.observe(target))
})
</script>

<template>
  <div class="page">
    <div class="page-bg"></div>

    <Header />

    <main class="snap-wrap">
      <HeroSection />
      <AboutSection />
      <HistorySection />
      <VisionSection />
      <ProductSection />
      <ContactSection />
    </main>

    <Footer />
  </div>
</template>