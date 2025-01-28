<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

// Gallery image sources
const galleryImages = Array.from(
  { length: 12 },
  (_, i) => `https://idox9vv.sufydely.com/Gallery/${i + 1}.webp`
);
</script>

<template>
  <!-- Gallery Section -->
  <section id="gallery" class="section-container bg-gray-50">
    <div class="max-w-5xl mx-auto px-8">
      <h2 class="section-title">Gallery</h2>
      <Swiper
        :modules="[Navigation, Pagination, Autoplay]"
        :slides-per-view="1"
        :space-between="20"
        :navigation="true"
        :pagination="{ clickable: true }"
        :autoplay="{ delay: 5000 }"
        class="w-full max-w-xl mx-auto mt-8"
      >
        <SwiperSlide v-for="(image, index) in galleryImages" :key="index" class="mt-4">
          <div class="aspect-square bg-gray-200 rounded-lg overflow-hidden">
            <!-- Lazy loaded image -->
            <img
              :src="image"
              loading="lazy"
              alt="Gallery Image"
              class="w-full h-full object-cover"
            />
          </div>
        </SwiperSlide>
      </Swiper>
    </div>
  </section>
</template>
