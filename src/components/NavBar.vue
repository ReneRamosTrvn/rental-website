<template>
  <main>
    <div
      class="w-full z-50 text-center px-40 flex fixed py-5 bg-stone-300 justify-center space-x-3"
    >
      <div v-for="route in routes" :key="route.route">
        <router-link :to="route.route">
          <button
            class="hover:text-stone-600 hover:border-stone-600 font-semibold border-black border-b-2 p-2"
          >
            {{ route.name }}
          </button>
        </router-link>
      </div>
    </div>
  </main>
</template>

<script setup>
import { RouterLink } from "vue-router";

const routes = [
  {
    name: "Home",
    route: "/",
  },
  {
    name: "Cars",
    route: "/cars",
  },
  // {
  //   name: "About",
  //   route: "/",
  // },
  // {
  //   name: "Login",
  //   route: "/",
  // },
];
</script>
