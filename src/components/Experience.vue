<script setup lang="ts">
import { ref } from 'vue';
import { Collapse } from 'vue-collapsed';

interface Experience {
  title: string;
  company: string;
  period: string;
  description: string;
  details: string[];
}

const experiences: Experience[] = [
  {
    title: 'Livestreaming Supervisor',
    company: 'PT. Antarestar Global Kreativindo (Antarestar)',
    period: 'Juli 2024 – Oktober 2024',
    description: '',
    details: [
      'Bertanggung jawab sebagai livestreaming operator 4 studio agar dapat berjalan dengan baik dan memastikan set studio yang menarik untuk live selama livestreaming berlangsung. Berhasil menjalankan live 100% tanpa terkendala.',
      'Mengatur strategi penjualan yang efektif dalam live dan menganalisa product yang optimal untuk di push saat livestreaming berjalan melalui dashboard. Berhasil mencapai target sales untuk semua studio dengan tingkat keberhasilan 85% setiap kali campaign.',
      'Bertanggung jawab atas host livestreaming untuk product knowledge, KPI, melatih pembawaan host dan mengatur jadwal host. Berhasil memastikan host untuk mencapai target sales dengan tingkat keberhasilan 75%.',
      'Merancang strategi promosi untuk meningkatkan sales, menganalisa tren pasar dan kompetitor untuk menyesuaikan strategi penjualan yang efektif.',
    ],
  },
  {
    title: 'Livestreaming Staff',
    company: 'PT. Pongo Technology Indonesia (Pongo Indonesia)',
    period: 'Februari 2024 – Juni 2024',
    description: '',
    details: [
      'Bertanggung jawab sebagai livestreaming operator untuk platform Tiktok, Shopee & Tokopedia, berhasil mengelola lebih dari 15 klien yang bekerjasama dengan PT Pongo Technology Indonesia.',
      'Menciptakan set studio yang menarik untuk live dan mengoptimalkan sales selama livestream berlangsung, berhasil memastikan live berjalan dengan lancar 100 % tanda terkendala teknis.',
      'Menganalisis product yang optimal untuk di push melalui dashboard secara realtime, berhasil mencapai target sales yang ditentukan hingga melebihi 90% dari target sales.',
      'Merencanakan konten yang sesuai untuk platform tiktok untuk menarik traffic kedalam live.',
    ],
  },
  {
    title: 'Social Media Specialist Leader',
    company: 'Kreatif Media Artisan',
    period: 'Juni 2023 – Januari 2024',
    description: '',
    details: [
      'Mengelola akun Instagram, Tiktok & Youtube. Berhasil meningkatkan followers minimal 500 setiap bulannya melalui strategi konten yang relevan.',
      'Merancang strategi konten setiap bulannya untuk platform Instagram, Tiktok dan Youtube. Berhasil memproduksi yang konsisten setidaknya 30 konten Instagram, 30 konten tiktok & 8 video youtube setiap bulannya.',
      'Merancang konsep ide konten setiap bulannya dan menentukan target social media untuk platform Instagram, tiktok & youtube, menganalisa efektivitas konten yang di upload yang bertujuan meningkatkan engagement.',
      'Bertanggung jawab sebagai leader tim social media agar dapat berjalan sesuai dengan target yang sudah di tetapkan.',
    ],
  },
  {
    title: 'Support Program Online & Offline',
    company: 'PT. Sukses Belajar Kuliner (Foodizz Academy)',
    period: 'Juli 2023 – September 2023',
    description: '',
    details: [
      'Mengelola lebih dari 80 F&B business Owner yang mengikuti Program Zero to Hero & Program Merchant yang merupakan program kolaborasi Foodizz Academy & Gojek, berhasil mendapatkan feedback positif dan mendapatkan minim keluhan dari form yang telah diberikan setiap bulannya.',
      'Bertanggung jawab sebagai livestreaming operator untuk online class menggunakan platform Zoom dan OBS Studio, berhasil menjalankan live 100% tanpa terkendala.',
      'Bertanggung jawab sebagai offline operator dalam kegiatan Seminar Program F&B Nastional Roadshoaw kolaborasi antara Foodizz Academy & PT Esensi Solusi Buana (ESB) untuk 5 Kota, berhasil memastikan kegiatan berjalan dengan lancar 100%',
    ],
  },
  {
    title: 'Supporting Program Online & Offline Internship',
    company: 'PT. Sukses Belajar Kuliner (Foodizz Academy)',
    period: 'Desember 2022 – Juli 2023',
    description: '',
    details: [
      'Mengelola 300 users yang mengikuti program sekolah bisnis kuliner, berhasil menghandle user dengan minim keluhan setiap bulannya dari form evaluasi yang diberikan.',
      'Merancang online event setiap bulannya untuk program sekolah bisnis kuliner, berhasil melaksanakan minimal 4 online event sekolah bisnis kuliner.',
      'Bertanggung jawab sebagai livestreaming operator untuk online event sekolah bisnis kuliner di platform zoom, berhasil menjalankan live 100% tanpa terkendala.',
    ],
  },
  {
    title: 'Offline Marketing Program & Livestreaming Specialist',
    company: 'PT. Daesang Agung Indonesia (Mamasuka)',
    period: 'April 2022 – Maret 2023',
    description: '',
    details: [
      'Bertanggung jawab sebagai Project Manager Offline Marketing, berhasil menjalankan 2 mobile legend competition offline competition di Jakarta dan Bogor.',
      'Bertanggung jawab merancang strategi event dimulai dari konsep sampai dengan pelaksanaan kegiatan, berhasil menjalankan event dengan keberhasilan 100% dan berhasil mendapatkan minimal 50 tim yang berpartisipasi dalam event.',
      'Bertanggung jawab sebagai livestreaming operator di platform youtube dan tiktok, berhasil memastikan live berjalan 100% tanpa kendala dan mendatangkan 1000 viewers.',
    ],
  },
  {
    title: 'Social Media Specialist & Livestreaming Specialist',
    company: 'Creative Ads Media Partner',
    period: 'Juni 2021 – Desember 2021',
    description: '',
    details: [
      'Mengelola akun Instagram & Youtube, meningkatkan followers minimal 50% setiap bulannya melalui strategi konten yang relevan.',
      'Merancang konten social media untuk platform Instagram, memproduksi 2 konten minimal setiap harinya. Menganalisa efektivitas konten yang di upload yang bertujuan meningkatkan engagement.',
      'Mengatur strategi promosi untuk bekerjasama dengan klien, berhasil bekerjasama dengan 2 minimal klien setiap bulannya sebagai media partner livestreaming.',
      'Bertanggung jawab sebagai livestreaming operator di platform youtube dan Instagram. Berhasil mengelola audio & video, mengatur overlay, transisi dan elemen dengan tingkat keberhasilan 100%.',
    ],
  },
  {
    title: 'Founder  & Social Media Specialist',
    company: 'Kintamani Bakery & Coffee',
    period: 'Januari 2020 – November 2021',
    description: '',
    details: [
      'Mendirikan kintamani bakery & coffee dengan konsep bakery & coffee dengan nuansa bali pertama di bekasi.',
      'Mengelola sebagai admin social media untuk platform Instagram dan Whatsapp, menganalisis efektivitas konten yang diupload untuk meningkatkan engagement customer.',
      'Menentukan strategi konten setiap bulannya untuk platform Instagram, berhasil memproduksi konten setidaknya 15 konten setiap bulannya.',
      'Merancang online & offline marketing event setiap bulan untuk semua social media kintamani bakery & coffee, berhasil menjalankan online & offline event 1 kali tiap bulannya.',
      'Merancang strategi penjualan online & offline dan berhasil meningkatkan sales pada saat soft opening sebesar 2 kali lipat dibanding sales harian.',
    ],
  },
  {
    title: 'Livestreaming Manager',
    company: 'Himpunan Borobudur Media Partner',
    period: 'Juli 2020 – Mei 2021',
    description: '',
    details: [
      'Bertanggung jawab sebagai live streaming operator di youtube & instagram sebagai media partner live streaming, berhasil menjalankan live 100% tanpa terkendala dan mendatangkan views minimal 500.',
      'Mengelola sebagai admin social media untuk platform Instagram & Youtube, berhasil meningkatkan followers 20% tiap bulannya.',
      'Membuat perencanaan konten social media, agenda event dan bekerjasama dengan coffee shop sebagai media partner, menganalisa efektivitas konten social media yang di publish.',
      'Merancang strategi promosi event kerjasama dengan coffee shop dan berhasil menyelenggarakan event dengan minimal 90 peserta.',
      'Mengelola kerjasama dengan kafe untuk mempersiapkan event dan berhasil bekerjasama dengan kafe yang di Bekasi tiap bulannya minimal 1 kafe.',
    ],
  },
];

const expandedExperiences = ref<Set<number>>(new Set());

const toggleExpand = (index: number) => {
  if (expandedExperiences.value.has(index)) {
    expandedExperiences.value.delete(index);
  } else {
    expandedExperiences.value.add(index);
  }
};
</script>

<template>
  <section id="experience" class="section-container bg-gray-50 relative">
    <div class="max-w-7xl mx-auto">
      <h2 class="section-title">Work Experience</h2>
      <div class="relative">
        <div class="timeline-line"></div>
        <div class="space-y-12">
          <div v-for="(exp, index) in experiences" :key="index" class="relative">
            <div class="timeline-dot"></div>
            <div
              :class="[
                'w-full md:w-5/12',
                index % 2 === 0 ? 'md:ml-auto md:pl-8' : 'md:mr-auto md:pr-8',
              ]"
            >
              <div class="bg-white p-6 rounded-lg shadow-md">
                <h3 class="text-xl font-semibold text-gold mb-2">{{ exp.title }}</h3>
                <p class="font-medium text-gray-800 mb-2">{{ exp.company }}</p>
                <p class="text-normal text-gray-600 mb-2">{{ exp.period }}</p>
                <!-- <p class="mb-4">{{ exp.description }}</p> -->

                <button
                  @click="toggleExpand(index)"
                  class="text-gold hover:text-gold-dark transition-colors duration-200 text-sm font-medium"
                >
                  {{ expandedExperiences.has(index) ? 'Show Less' : 'Show More' }}
                </button>

                <Collapse :when="expandedExperiences.has(index)">
                  <div class="mt-2 space-y-2">
                    <ul class="list-disc list-inside space-y-2 text-sm text-gray-600">
                      <li
                        v-for="detail in exp.details"
                        :key="detail"
                        class="transition-all duration-300 leading-relaxed text-justify hover:text-black"
                      >
                        {{ detail }}
                      </li>
                    </ul>
                  </div>
                </Collapse>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
