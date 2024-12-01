<script setup lang="ts">
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import CareerInterests from './components/CareerInterests.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
import Education from './components/Education.vue';
import Certifications from './components/Certifications.vue';
import Portfolio from './components/Portfolio.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <div class="min-h-screen">
    <Navbar />
    <main>
      <Hero />
      <About />
      <CareerInterests />
      <Skills />
      <Experience />
      <Education />
      <Certifications />
      <Portfolio />
      <Contact />
    </main>
    <Footer />
  </div>
</template>
