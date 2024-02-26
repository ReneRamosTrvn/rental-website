<template>
  <main>
    <div class="px-10 lg:px-20 pb-10 bg-stone-100">
      <div class="grid grid-cols-2 lg:grid-cols-4 space-x-2">
        <div
          class="flex justify-center my-5 lg:my-0"
          v-for="logo in logos"
          :key="logo.alt"
        >
          <img class="h-16" :src="logo.src" :alt="logo.alt" />
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import fordLogo from "/public/ford.png";
import subaruLogo from "/public/subaru.png";
import nissanLogo from "/public/nissan.png";
import mazdaLogo from "/public/mazda.png";

const logos = [
  {
    src: fordLogo,
    alt: "ford-logo",
  },
  {
    src: subaruLogo,
    alt: "subaru-logo",
  },
  {
    src: nissanLogo,
    alt: "nissan-logo",
  },
  {
    src: mazdaLogo,
    alt: "mazda-logo",
  },
];
</script>
