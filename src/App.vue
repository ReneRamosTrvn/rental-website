<template>
  <NavBar
    :class="
      scrolledDown
        ? ' opacity-0 transition-opacity duration-500'
        : ' opacity-100 transition-opacity duration-500'
    "
  />
  <RouterView />
  <Footer />
</template>

<script setup>
import { ref, onMounted } from "vue";
import NavBar from "./components/NavBar.vue";
import Footer from "./components/Footer.vue";

const scrolledDown = ref(false);
const scrolledUp = ref(true);

onMounted(() => {
  let lastScrollTop = 0;

  window.addEventListener("scroll", () => {
    const st = window.pageYOffset || document.documentElement.scrollTop;
    if (st > lastScrollTop) {
      scrolledDown.value = true;
      scrolledUp.value = false;
    } else {
      scrolledDown.value = false;
      scrolledUp.value = true;
    }
    lastScrollTop = st <= 0 ? 0 : st;
  });
});
</script>
