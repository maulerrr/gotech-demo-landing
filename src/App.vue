<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue';
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Benefits from "./components/Benefits.vue";
import Features from "./components/Features.vue";
import Services from "./components/Services.vue";
import HowItWorks from "./components/HowItWorks.vue";
import Sponsors from "./components/Sponsors.vue";
import Testimonials from "./components/Testimonials.vue";
import Team from "./components/Team.vue";
import Pricing from "./components/Pricing.vue";
import Community from "./components/Community.vue";
import Contact from "./components/Contact.vue";
import FAQ from "./components/FAQ.vue";
import Footer from "./components/Footer.vue";

// Reactive cursor coordinates in pixels
const mouseX = ref(0);
const mouseY = ref(0);

// Update on every global mouse move
function updateCursorPosition(e: MouseEvent) {
  mouseX.value = e.clientX;
  mouseY.value = e.clientY;
}

onMounted(() => window.addEventListener('mousemove', updateCursorPosition));
onUnmounted(() => window.removeEventListener('mousemove', updateCursorPosition));

// Compute a radial-gradient at the current pixel coords
const gradientStyle = computed(() => ({
  background: `radial-gradient(circle 500px at ${mouseX.value}px ${mouseY.value}px, rgba(0,94,212,0.4) 0%, rgba(0,20,40,0.8) 100%)`,
  backgroundRepeat: 'no-repeat'
}));
</script>

<template>
  <!-- Full-screen gradient overlay fixed to viewport -->
  <div class="fixed inset-0 pointer-events-none z-0" :style="gradientStyle" aria-hidden="true" />

  <!-- Main content scrolls normally above the gradient -->
  <div class="relative z-10">
    <Navbar />
    <Hero />
    <Sponsors />
    <Benefits />
    <Features />
    <Services />
    <Contact />
    <Footer />
  </div>
</template>
