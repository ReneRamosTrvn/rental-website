<script setup>
import Finder from "@/components/Finder.vue";
import Brands from "@/components/Brands.vue";
import PopularCars from "@/components/popularCars.vue";
import Testimonials from "@/components/Testimonials.vue";
</script>

<template>
  <main>
    <div
      class="bg-stone-300 w-full lg:h-screen flex flex-wrap-reverse justify-center items-center"
    >
      <div class="w-full lg:w-1/2 px-10 lg:px-20 pb-20 lg:pb-0">
        <h1
          class="text-4xl lg:text-[60px] font-semibold lg:leading-[55px] mb-5"
        >
          Rent your favorite car in
          <span class="text-red-600">Easy</span> steps.
        </h1>
        <p class="text-lg leading-7 text-gray-600">
          Get a car wherever and whenever you need it with tou Android or iOS
          device.
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="w-6 h-6"
          >
            <path d="M10.5 18.75a.75.75 0 0 0 0 1.5h3a.75.75 0 0 0 0-1.5h-3Z" />
            <path
              fill-rule="evenodd"
              d="M8.625.75A3.375 3.375 0 0 0 5.25 4.125v15.75a3.375 3.375 0 0 0 3.375 3.375h6.75a3.375 3.375 0 0 0 3.375-3.375V4.125A3.375 3.375 0 0 0 15.375.75h-6.75ZM7.5 4.125C7.5 3.504 8.004 3 8.625 3H9.75v.375c0 .621.504 1.125 1.125 1.125h2.25c.621 0 1.125-.504 1.125-1.125V3h1.125c.621 0 1.125.504 1.125 1.125v15.75c0 .621-.504 1.125-1.125 1.125h-6.75A1.125 1.125 0 0 1 7.5 19.875V4.125Z"
              clip-rule="evenodd"
            />
          </svg>
        </p>
      </div>
      <div class="w-full lg:w-1/2 py-20 lg:py-0">
        <img src="/public/tiguan.png.png" alt="tiguan" class="object-cover" />
      </div>
    </div>
    <Finder />
    <Brands />
    <PopularCars />
    <Testimonials />
  </main>
</template>
