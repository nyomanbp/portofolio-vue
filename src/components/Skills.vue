<script setup lang="ts">
interface Skill {
  name: string;
  icon: string;
  type: string;
}

const skills: Skill[] = [
  // Streaming Apps
  { name: 'OBS Studio', icon: '🎥', type: 'Live Streaming' },
  { name: 'Vmix', icon: '🎬', type: 'Live Streaming' },
  // Video Editing
  { name: 'Adobe Premiere', icon: '🎥', type: 'Editing Video' },
  { name: 'Capcut', icon: '✂️', type: 'Editing Video' },
  { name: 'Adobe After Effects', icon: '✨', type: 'Editing Video' },
  // Design & Office
  { name: 'Adobe Photoshop', icon: '🎨', type: 'Design' },
  { name: 'Adobe Illustrator', icon: '✏️', type: 'Design' },
  { name: 'Blender', icon: '🎭', type: 'Design' },
  { name: 'Microsoft Office', icon: '📊', type: 'Office' },
];
</script>

<template>
  <section id="skills" class="section-container bg-white">
    <div class="max-w-5xl mx-auto">
      <h2 class="section-title">Skills</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div
          v-for="skill in skills"
          :key="skill.name"
          class="hover-card group bg-gray-50 rounded-lg py-10 md:p-8 text-center"
        >
          <div class="text-4xl mb-3 group-hover:scale-110 transition-transform duration-300">
            {{ skill.icon }}
          </div>
          <h4 class="font-semibold">{{ skill.name }}</h4>
          <p class="text-sm text-gray-600 mt-1">{{ skill.type }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
