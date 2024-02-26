<template>
  <main>
    <div class="w-full px-5 lg:px-20 py-20 bg-stone-100">
      <Finder class="py-10" />
      <div class="grid grid-cols-1 lg:grid-cols-2">
        <div
          v-for="car in Cars"
          class="bg-white transition-colors duration-500 rounded-lg grid grid-cols-2 shadow-sm m-2"
        >
          <div
            class="bg-stone-200 rounded-l-lg flex justify-center items-center"
          >
            <img
              :src="car.img"
              alt="car-photo"
              class="object-cover mb-5 w-full"
            />
          </div>
          <div class="p-5 lg:p-10">
            <p class="text-lg text-center">
              {{ car.name }}
            </p>
            <p class="text-green-600 text-center font-semilight text-md mb-5">
              ${{ car.price }}USD /day
            </p>
            <div class="text-center mt-5">
              <button
                class="px-5 py-2 bg-red-700 hover:bg-red-600 text-white rounded-full"
              >
                View Deal
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref, onMounted, reactive } from "vue";
import tiguanPhoto from "/tiguan.png.png";
import maximaPhoto from "/maxima.png";
import cx5Phtono from "/cx5.webp";
import m5 from "/m5-comp.png";
import r8 from "/r8.avif";
import rs6 from "/rs6.png";
import Finder from "../components/Finder.vue";

const Cars = reactive([
  {
    name: "BMW M5 Competition",
    img: m5,
    price: 32,
    specs: {
      trans: "AWD",
      hp: "290",
      topSpeed: "180",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "18/23 mpg",
    },
  },
  {
    name: "Audi R8 Spyder",
    img: r8,
    price: 28,
    specs: {
      trans: "FWD",
      hp: "180",
      topSpeed: "100",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "21/24 mpg",
    },
  },
  {
    name: "Audi RS6",
    img: rs6,
    price: 30,
    specs: {
      trans: "FWD",
      hp: "210",
      topSpeed: "130",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "20/21 mpg",
    },
  },
  {
    name: "Volkswagen Tiguan RS 2024",
    img: tiguanPhoto,
    price: 32,
    specs: {
      trans: "AWD",
      hp: "290",
      topSpeed: "180",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "18/23 mpg",
    },
  },
  {
    name: "Nissan Maxima 2024",
    img: maximaPhoto,
    price: 28,
    specs: {
      trans: "FWD",
      hp: "180",
      topSpeed: "100",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "21/24 mpg",
    },
  },
  {
    name: "Mazda CX5 2024",
    img: cx5Phtono,
    price: 30,
    specs: {
      trans: "FWD",
      hp: "210",
      topSpeed: "130",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "20/21 mpg",
    },
  },
  {
    name: "Mazda CX5 2024",
    img: cx5Phtono,
    price: 30,
    specs: {
      trans: "FWD",
      hp: "210",
      topSpeed: "130",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "20/21 mpg",
    },
  },
  {
    name: "Mazda CX5 2024",
    img: cx5Phtono,
    price: 30,
    specs: {
      trans: "FWD",
      hp: "210",
      topSpeed: "130",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "20/21 mpg",
    },
  },
  {
    name: "Mazda CX5 2024",
    img: cx5Phtono,
    price: 30,
    specs: {
      trans: "FWD",
      hp: "210",
      topSpeed: "130",
      infotaiment: "Carplay",
      typeOfFuel: "Gas",
      consumption: "20/21 mpg",
    },
  },
]);
</script>
