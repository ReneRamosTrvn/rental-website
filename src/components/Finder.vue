<template>
  <main>
    <div class="w-full bg-stone-100 px-10 lg:px-20 py-20">
      <div class="flex flex-wrap bg-white p-5 lg:p-10 rounded-xl">
        <div class="w-full lg:w-1/4 lg:border-r border-black px-2 py-5 lg:py-0">
          <label class="w-full font-semibold" for="location">Location</label>
          <select
            class="w-full border border-gray-300 p-2 rounded-md"
            name="location"
          >
            <option v-for="location in storeLocations" :key="index">
              {{ location }}
            </option>
          </select>
        </div>
        <div class="w-full lg:w-1/4 lg:border-r border-black px-2 py-5 lg:py-0">
          <label class="w-full font-semibold" for="location"
            >Pick-up date</label
          >
          <VueDatePicker
            class=""
            v-model="pickupDate"
            disable-year-select
            time-picker-inline
            :start-time="startTime"
            :enable-time-picker="false"
            :min-date="new Date()"
            auto-apply
            :month-change-on-scroll="false"
          />
        </div>
        <div class="w-full lg:w-1/4 px-2 py-5 lg:py-0">
          <label class="w-full font-semibold" for="location">Return date</label>
          <VueDatePicker
            v-model="returnDate"
            disable-year-select
            time-picker-inline
            :start-time="startTime"
            :enable-time-picker="false"
            :min-date="pickupDate"
            auto-apply
            :month-change-on-scroll="false"
          />
        </div>
        <div
          class="w-full lg:w-1/4 text-center py-5 lg:py-0 flex items-center justify-center"
        >
          <router-link
            v-if="pickupDate && returnDate"
            class="w-2/3 px-5 py-2 bg-red-700 hover:bg-red-600 text-white font-semibold rounded-full"
            to="/cars"
          >
            <button>Search</button>
          </router-link>
          <button
            v-if="!pickupDate || !returnDate"
            :disabled="!pickupDate || !returnDate"
            class="w-2/3 px-5 py-2 bg-gray-700 text-white font-semibold rounded-full"
          >
            Search
          </button>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { RouterLink } from "vue-router";

const pickupDate = ref(null);
const returnDate = ref(null);
const startTime = ref({ hours: 0, minutes: 0 });

onMounted(() => {});

function validateReturnDate() {
  console.log(returnDate);
}
const storeLocations = [
  "Dallas, Texas",
  "Mesquite, Texas",
  "Forth Worth, Texas",
  "Austin, Texas",
  "Houston, Texas",
  "Moon, Milkyway",
];
</script>
