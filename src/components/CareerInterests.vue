<script setup lang="ts">
import { ref } from 'vue';

interface CareerPath {
  title: string;
  icon: string;
  roles: string[];
}

const careerPaths: CareerPath[] = [
  {
    title: 'Live Stream Specialist',
    icon: '🎥',
    roles: [
      'Livestreaming Supervisor',
      'Livestreaming Staff',
      'Online Livestreaming Operator',
      'Offline Livestreaming Operator',
    ],
  },
  {
    title: 'Social Media Specialist',
    icon: '📱',
    roles: ['Social Media Admin', 'Graphic Designer', 'Content Planner'],
  },
  {
    title: 'E-Commerce Specialist',
    icon: '🛍️',
    roles: ['Livestream Host'],
  },
];

const hoveredPath = ref<string | null>(null);
</script>

<template>
  <section id="career" class="section-container bg-gray-50">
    <div class="max-w-7xl mx-auto">
      <h2 class="section-title">Career Interests</h2>
      <div class="grid md:grid-cols-3 gap-8 pt-24">
        <div
          v-for="path in careerPaths"
          :key="path.title"
          class="relative"
          @mouseenter="hoveredPath = path.title"
          @mouseleave="hoveredPath = null"
        >
          <div
            class="bg-white p-8 rounded-lg shadow-md transition-all duration-500 py-16"
            :class="{ 'transform -translate-y-2': hoveredPath === path.title }"
          >
            <div class="text-4xl mb-4 text-center">{{ path.icon }}</div>
            <h3 class="text-xl font-semibold mb-4 text-center">{{ path.title }}</h3>

            <transition
              enter-active-class="transition ease-out duration-300"
              enter-from-class="transform opacity-0 scale-95"
              enter-to-class="transform opacity-100 scale-100"
              leave-active-class="transition ease-in duration-200"
              leave-from-class="transform opacity-100 scale-100"
              leave-to-class="transform opacity-0 scale-95"
            >
              <div
                v-if="hoveredPath === path.title"
                class="absolute inset-0 bg-black bg-opacity-90 rounded-lg p-6 flex items-center justify-center"
              >
                <ul class="text-white space-y-3">
                  <li v-for="role in path.roles" :key="role" class="text-center text-gold">
                    {{ role }}
                  </li>
                </ul>
              </div>
            </transition>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
