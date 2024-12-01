<script setup lang="ts">
interface Education {
  degree: string;
  school: string;
  period: string;
  gpa: string;
  description: string;
  achievements: string[];
}

const education: Education[] = [
  // {
  //   degree: 'D4 Teknologi Rekayasa Multimedia',
  //   school: 'Politeknik Negeri Media Kreatif',
  //   period: '2020 - 2024',
  //   gpa: 'IPK: 3.72/4.00',
  //   description: 'Specialized in digital content creation and media management.',
  //   achievements: [
  //     'Graduated with First Class Honours',
  //     'Led student media production team',
  //     'Completed internship at major media company',
  //     'Received Excellence in Digital Media award',
  //   ],
  // },
  {
    degree: 'D4 Teknologi Rekayasa Multimedia',
    school: 'Politeknik Negeri Media Kreatif',
    period: '2020 - 2024',
    gpa: 'IPK: 3.72/4.00',
    description: '',
    achievements: [],
  },
  {
    degree: 'Matematika dan Ilmu Pengetahuan Alam',
    school: 'SMA Negeri 13 Kota Bekasi',
    period: '2017-2020',
    gpa: '',
    description: '',
    achievements: [],
  },
];
</script>

<template>
  <section id="education" class="section-container bg-white">
    <div class="max-w-3xl mx-auto">
      <h2 class="section-title">Education</h2>
      <div
        v-for="(edu, index) in education"
        :key="index"
        class="bg-gray-50 p-8 rounded-lg shadow-md hover-card mb-12"
      >
        <h3 class="text-xl font-semibold text-gold mb-4">{{ edu.degree }}</h3>
        <p class="font-semibold text-gray-700 mb-2">{{ edu.school }}</p>
        <p class="font-medium text-gray-700 mb-2">{{ edu.period }}</p>
        <p class="font-semibold text-gray-700 mb-4">{{ edu.gpa }}</p>
        <!-- <p class="mb-6">{{ edu.description }}</p> -->
        <!-- <div>
          <h4 class="font-medium mb-3">Key Achievements:</h4>
          <ul class="list-disc list-inside space-y-2 text-gray-600">
            <li
              v-for="achievement in edu.achievements"
              :key="achievement"
              class="transition-all duration-300 hover:text-black"
            >
              {{ achievement }}
            </li>
          </ul>
        </div> -->
      </div>
    </div>
  </section>
</template>
