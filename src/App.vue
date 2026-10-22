<script setup>
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import StorySection from './components/StorySection.vue'
import MenuSection from './components/MenuSection.vue'
import SpaceSection from './components/SpaceSection.vue'
import VisitSection from './components/VisitSection.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <SiteHeader />
  <main id="top">
    <HeroSection />
    <StorySection />
    <MenuSection />
    <SpaceSection />
    <VisitSection />
  </main>
  <SiteFooter />
</template>

