<template>
  <main>
    <div
      :class="
        casual
          ? 'p-10 lg:p-20 pb-10 bg-stone-200 transition-colors duration-500'
          : 'p-10 lg:p-20 pb-10 bg-black transition-colors duration-500'
      "
    >
      <div
        :class="
          casual
            ? 'w-full text-center text-4xl font-semibold mb-10 transition-colors duration-500'
            : 'text-white w-full text-center text-4xl font-semibold mb-10 transition-colors duration-500'
        "
      >
        Most popular cars rental deals
      </div>
      <div class="w-full flex justify-center">
        <button
          @click="(casual = true), (fast = false)"
          :class="
            casual
              ? 'm-5 text-lg font-semibold border-b border-black transition-colors duration-500'
              : 'text-white m-5 text-lg font-md transition-colors duration-500'
          "
        >
          Casual
        </button>
        <button
          @click="(casual = false), (fast = true)"
          :class="
            fast
              ? 'text-white m-5 text-lg font-semibold border-b border-white '
              : 'm-5 text-lg font-md '
          "
        >
          Go fast
        </button>
      </div>
      <div class="grid grid-cols-1 lg:grid-cols-3 lg:space-x-3">
        <div
          v-for="car in choosePopularCars()"
          class="p-5 lg:p-10 rounded-lg flex flex-col justify-between my-5 lg:my-0 shadow-sm"
          :class="
            casual
              ? 'bg-white transition-colors duration-500'
              : 'bg-none border-gray-600 border transition-colors duration-500'
          "
        >
          <img :src="car.img" alt="car-photo" class="object-cover mb-5" />
          <div>
            <p
              class="text-lg text-center"
              :class="
                casual
                  ? 'transition-colors duration-500'
                  : 'text-white transition-colors duration-500'
              "
            >
              {{ car.name }}
            </p>
            <p class="text-green-600 text-center font-semilight text-md mb-5">
              ${{ car.price }}USD /day
            </p>
            <div
              class="grid grid-cols-2"
              :class="
                casual
                  ? 'text-gray-600 transition-colors duration-500'
                  : 'text-white transition-colors duration-500'
              "
            >
              <p>Top Speed: {{ car.specs.topSpeed }}</p>
              <p>Hp: {{ car.specs.hp }}</p>
              <p>Traction: {{ car.specs.trans }}</p>
              <p>{{ car.specs.infotaiment }}</p>
              <p>Fuel: {{ car.specs.typeOfFuel }}</p>
              <p>Consumption: {{ car.specs.consumption }}</p>
            </div>
          </div>
          <div class="text-center mt-5">
            <button
              class="px-5 py-2 bg-red-700 hover:bg-red-600 text-white rounded-full"
            >
              Rent Now
            </button>
          </div>
        </div>
      </div>
      <div class="w-full text-center mt-10">
        <router-link to="/cars">
          <p class="underline">See All</p>
        </router-link>
      </div>
    </div>
  </main>
</template>

<script setup>
import tiguanPhoto from "/tiguan.png.png";
import maximaPhoto from "/maxima.png";
import cx5Phtono from "/cx5.webp";
import m5 from "/m5-comp.png";
import r8 from "/r8.avif";
import rs6 from "/rs6.png";
import { ref, computed, reactive } from "vue";

let casual = ref(true);
let fast = ref(false);

function choosePopularCars() {
  if (casual.value == true) {
    return popularCars;
  }
  if (fast.value == true) {
    return popularSportCars;
  } else {
    return null;
  }
}

const popularSportCars = reactive([
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
]);

const popularCars = reactive([
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
]);
</script>
