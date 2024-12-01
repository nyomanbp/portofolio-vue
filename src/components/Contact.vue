<script setup lang="ts">
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faPhone, faEnvelope } from '@fortawesome/free-solid-svg-icons';
import { faInstagram, faLinkedin } from '@fortawesome/free-brands-svg-icons';

library.add(faPhone, faEnvelope, faInstagram, faLinkedin);

interface ContactInfo {
  type: string;
  value: string;
  icon: [string, string]; // Use icon names
  link?: string;
}

const contacts: ContactInfo[] = [
  {
    type: 'Phone',
    value: '081905235448',
    icon: ['fas', 'phone'],
    link: 'tel:+6281905235448',
  },
  {
    type: 'Email',
    value: 'nyomanbaihaqie4@gmail.com',
    icon: ['fas', 'envelope'],
    link: 'mailto:nyomanbaihaqie4@gmail.com',
  },
  {
    type: 'Instagram',
    value: '@nyoman_bp',
    icon: ['fab', 'instagram'],
    link: 'https://www.instagram.com/nyoman_bp',
  },
  {
    type: 'LinkedIn',
    value: 'Nyoman Baihaqie Putra',
    icon: ['fab', 'linkedin'],
    link: 'https://www.linkedin.com/in/nyomanbp/',
  },
];
</script>

<template>
  <section id="contact" class="pt-24 pb-16 md:py-20 md:pb-28 bg-black text-white">
    <div class="container mx-auto px-4">
      <h2 class="section-title">Get in Touch</h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-6xl mx-auto">
        <a
          v-for="contact in contacts"
          :key="contact.type"
          :href="contact.link"
          target="_blank"
          rel="noopener noreferrer"
          class="bg-gray-900 p-6 rounded-lg text-center hover-card"
        >
          <div class="text-3xl mb-3">
            <font-awesome-icon :icon="contact.icon" />
          </div>
          <h3 class="font-semibold text-gold">{{ contact.type }}</h3>
          <p class="text-gray-300 break-words">{{ contact.value }}</p>
        </a>
      </div>
    </div>
  </section>
</template>
