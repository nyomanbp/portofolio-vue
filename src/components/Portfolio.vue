<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

interface Project {
  title: string;
  description: string;
  videoId: string;
}

const projects: Project[] = [
  {
    title: 'Pandawa Tournament 2021 Day-1',
    description: 'Livestream event production',
    videoId: 'hbQTLuh1mRM',
  },
  {
    title: 'Pandawa Tournament S2 2021',
    description: 'Livestream event production',
    videoId: 'HfPV9XfylHA',
  },
  {
    title: 'Pandawa Tournament S2 2021',
    description: 'Livestream event production',
    videoId: 'ViIo0_T25u4',
  },
  {
    title: '[FINAL DAY] SPTWN TURNAMEN SEASON 5',
    description: 'Livestream event production',
    videoId: 'umGZRhxEmEk',
  },
  // Add other projects here
  {
    title: '[FINAL DAY] Thunder Tournament Season 8',
    description: 'Livestream event production',
    videoId: '4TCxxLHqWL0',
  },
  {
    title: 'CSS TOURNAMENT S1 (FINAL DAY)',
    description: 'Livestream event production',
    videoId: 'miPCICx_coU',
  },
  {
    title: 'CSS TOURNAMENT S1 DAY 2 (GROUP PHASE)',
    description: 'Livestream event production',
    videoId: 'p9qhdVhB0Zk',
  },
  {
    title: 'PANDAWA TOURNAMENT DAY 1 (Group Phase)',
    description: 'Livestream event production',
    videoId: '5TUrgR4Ice8',
  },
  {
    title: '(SCRIMMAGE GAME) THUNDER vs DRAGONEST',
    description: 'Livestream event production',
    videoId: 'aAj9dAx8f0k',
  },
  {
    title: '(SCRIMMAGE GAME) VALHEIM vs DEVIL TEAM',
    description: 'Livestream event production',
    videoId: 'y9f4IDhgZKM',
  },
  {
    title: '(Mobile Legend) MAPPLE TOURNAMENT DAY 1',
    description: 'Livestream event production',
    videoId: 'L2mDJ9AF-U4',
  },
  {
    title: '(SEMI FINAL DAY) Marketing Mobile legend Competition Season 3',
    description: 'Livestream event production',
    videoId: 'rBF4gNVFqR4',
  },
  {
    title: '(FINAL DAY) Marketing Mobile legend Competition Season 3',
    description: 'Livestream event production',
    videoId: 'LAsJ65AjWWE',
  },
  {
    title: 'Main Event Mobile Legends OKP 2021 | Day 1',
    description: 'Livestream event production',
    videoId: 'wKvSrKKOFNo',
  },
  {
    title: 'Main Event Mobile Legends OKP 2021 | Day 2',
    description: 'Livestream event production',
    videoId: '0MPHcMaQVUI',
  },
  {
    title: 'Main Event Mobile Legends OKP 2021 | Day 3',
    description: 'Livestream event production',
    videoId: '2JC2z8SIA50',
  },
  {
    title: 'Main Event Mobile Legends OKP 2021 | Day 4',
    description: 'Livestream event production',
    videoId: 'X6OIgf2VeaU',
  },
];

const reversedProjects = [...projects].reverse();

import { ref } from 'vue';

const activeProjectIndex = ref(0);
const loadedVideos = ref(new Set<number>());

function onSlideChange(swiper: any) {
  activeProjectIndex.value = swiper.activeIndex;
}

function loadVideo(index: number) {
  loadedVideos.value.add(index);
}
</script>

<template>
  <section id="portfolio" class="pt-24 pb-44 md:py-24 md:mb-10 bg-white">
    <div class="container mx-auto px-4">
      <h2 class="section-title">Portfolio</h2>
      <Swiper
        :modules="[Navigation, Pagination, Autoplay]"
        :slides-per-view="1"
        :space-between="30"
        :navigation="true"
        :pagination="{ clickable: true }"
        :autoplay="{ delay: 10000 }"
        class="w-full max-w-4xl mx-auto mt-32 md:mt-0"
        @slideChange="onSlideChange"
      >
        <SwiperSlide
          v-for="(project, index) in reversedProjects"
          :key="project.title"
          @click="loadVideo(index)"
        >
          <div class="aspect-video bg-black rounded-lg overflow-hidden">
            <template v-if="loadedVideos.has(index)">
              <iframe
                :src="`https://www.youtube.com/embed/${project.videoId}`"
                class="w-full h-full"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen
              >
              </iframe>
            </template>
            <template v-else>
              <div
                class="relative w-full h-full flex items-center justify-center bg-gray-800 cursor-pointer"
                @click="loadVideo(index)"
              >
                <img
                  :src="`https://img.youtube.com/vi/${project.videoId}/hqdefault.jpg`"
                  alt="Video Thumbnail"
                  class="absolute inset-0 w-full h-full object-cover"
                />
                <div class="relative z-10 text-white">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24"
                    fill="currentColor"
                    class="w-12 h-12"
                  >
                    <path d="M8 5v14l11-7z" />
                  </svg>
                </div>
              </div>
            </template>
          </div>
        </SwiperSlide>
      </Swiper>
      <div class="mt-8 text-center">
        <h3 class="text-xl font-semibold">{{ reversedProjects[activeProjectIndex].title }}</h3>
        <p class="text-gray-600">{{ reversedProjects[activeProjectIndex].description }}</p>
      </div>
    </div>
  </section>
</template>
