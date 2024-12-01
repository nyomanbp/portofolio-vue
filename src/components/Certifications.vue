<script setup lang="ts">
import { library } from '@fortawesome/fontawesome-svg-core';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faBriefcase, faDesktop, faUsers, faWifi } from '@fortawesome/free-solid-svg-icons';
import { faFlutter } from '@fortawesome/free-brands-svg-icons';

library.add(faDesktop, faBriefcase, faUsers, faFlutter, faWifi);

interface Certification {
  name: string;
  issuer: string;
  date: string;
  icon: [string, string];
  link?: string;
}

const certifications: Certification[] = [
  {
    name: 'Junior Web Developer',
    issuer: 'Vocational School Graduate Academy (VSGA) - KOMINFO',
    date: '2021',
    icon: ['fas', 'desktop'],
    link: 'https://drive.google.com/drive/folders/14hb-epXEkAtsIAZ2R1wY7YAPKOLVZtmo?usp=drive_link',
  },
  {
    name: 'Digital Enterpreneurship Academy (DEA)',
    issuer: 'Digitalent Scholarship - KOMINFO',
    date: '2021',
    icon: ['fas', 'briefcase'],
    link: 'https://drive.google.com/drive/folders/1OfnwgFfNhV7ue2m3v5xoTumG9uPIxUyE?usp=drive_link',
  },
  {
    name: 'Interpersonal Skill',
    issuer: 'Digitalent Pasca Pelatihan – KOMINFO',
    date: '2021',
    icon: ['fas', 'users'],
    link: 'https://drive.google.com/drive/folders/1VegG6aIcK61G8bMVjCSU5nXvHSlxJ1A8?usp=drive_link',
  },
  {
    name: 'Flutter Mobile App Development',
    issuer: 'Candradimuka JABAR Coding Camp – PROVINSI JAWA BARAT',
    date: '2021',
    icon: ['fab', 'flutter'],
    link: 'https://drive.google.com/drive/folders/1RAwFgdQWObQOEkXgukO-JP6L3w9Uk15H?usp=drive_link',
  },
  {
    name: 'Networking Basic',
    issuer: 'Skill For All – CISCO',
    date: '2021',
    icon: ['fas', 'wifi'],
    link: '#',
  },
];
</script>

<template>
  <section id="certifications" class="section-container bg-gray-50">
    <div class="max-w-6xl mx-auto">
      <h2 class="section-title">Certifications</h2>

      <!-- Certifications Grid -->
      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="cert in certifications"
          :key="cert.name"
          class="bg-white p-6 rounded-lg shadow-md hover-card group flex flex-col justify-center text-center items-center min-h-[250px]"
        >
          <div class="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">
            <font-awesome-icon :icon="cert.icon" />
          </div>
          <h3 class="text-xl font-semibold text-gold mb-2">{{ cert.name }}</h3>
          <p class="text-gray-600 mb-1">{{ cert.issuer }}</p>
          <p class="text-sm text-gray-500">{{ cert.date }}</p>
          <a
            v-if="cert.link"
            :href="cert.link"
            class="text-gold hover:underline mt-4 inline-block text-sm"
            target="_blank"
          >
            View Certificate
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
