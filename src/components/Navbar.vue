<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
// import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline';
import { Bars3Icon } from '@heroicons/vue/24/outline';
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue';

const isScrolled = ref(false);
// const mobileMenuOpen = ref(false);

const sections = [
  { id: 'about', label: 'About' },
  { id: 'career', label: 'Interest' },
  { id: 'skills', label: 'Skills' },
  { id: 'experience', label: 'Experience' },
  { id: 'education', label: 'Education' },
  { id: 'certifications', label: 'Certifications' },
  { id: 'portfolio', label: 'Portfolio' },
  { id: 'gallery', label: 'Gallery' },
  { id: 'contact', label: 'Contact' },
];

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <nav
    :class="[
      'fixed w-full z-50 transition-all duration-300',
      isScrolled ? 'bg-white shadow-md py-2' : 'bg-transparent py-4',
    ]"
  >
    <div class="max-w-7xl mx-auto px-2 sm:px-4 lg:px-6">
      <div class="flex justify-between items-center">
        <a href="#" class="text-2xl font-bold text-gold">Portofolio</a>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex space-x-6">
          <a
            v-for="section in sections"
            :key="section.id"
            :href="'#' + section.id"
            class="nav-link text-gold"
          >
            {{ section.label }}
          </a>
        </div>

        <!-- Mobile Navigation -->
        <Menu as="div" class="md:hidden">
          <MenuButton class="p-2 rounded-md text-gray-700 hover:text-gold">
            <Bars3Icon class="h-6 w-6" />
          </MenuButton>

          <transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="transform scale-95 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-100 ease-in"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-95 opacity-0"
          >
            <MenuItems
              class="absolute right-0 mt-2 w-48 origin-top-right bg-white divide-y divide-gray-100 rounded-md shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none"
            >
              <div class="py-1">
                <MenuItem v-for="section in sections" :key="section.id" v-slot="{ active }">
                  <a
                    :href="'#' + section.id"
                    :class="[active ? 'bg-gray-100 text-gold' : 'text-gray-700', 'mobile-nav-link']"
                  >
                    {{ section.label }}
                  </a>
                </MenuItem>
              </div>
            </MenuItems>
          </transition>
        </Menu>
      </div>
    </div>
  </nav>
</template>
