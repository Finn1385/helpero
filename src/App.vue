<script setup lang="ts">
import NavBar from "./components/NavBar.vue";
import HeroSection from "./components/HeroSection.vue";
import WishlistSection from "./components/WishlistSection.vue";
import Footer from "./components/Footer.vue";
import AboutSection from "./components/ServicesSection.vue";
import TextSection from "./components/TextSection.vue";
</script>

<template>
  <NavBar />
  <div class="content">
    <HeroSection />
    <TextSection />
    <AboutSection />
    <WishlistSection />
    <Footer />
  </div>
</template>

<style scoped lang="scss">
* {
  --side-padding: 5rem;
}

.content {
  padding: 0 var(--side-padding);
}

@media (max-width: 1024px) {
  * {
    --side-padding: 3rem;
  }
}

@media (max-width: 768px) {
  * {
    --side-padding: 1.5rem;
  }
}

@media (max-width: 480px) {
  * {
    --side-padding: 1.25rem;
  }
}
</style>
