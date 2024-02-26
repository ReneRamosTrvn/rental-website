<template>
  <main class="bg-stone-100">
    <div class="p-20 w-full text-center text-4xl font-semibold">
      What people say about us?
    </div>
    <div class="pb-10 lg:px-72">
      <carousel
        :items-to-show="1"
        autoplay="5000"
        pauseAutoplayOnHover
        wrap-around="true"
      >
        <slide v-for="(user, index) in users" :key="index">
          <div class="w-full flex flex-wrap px-10">
            <img
              :src="user.picture.large"
              alt="client-avatar"
              class="h-full object-cover mx-auto rounded-3xl my-auto"
            />
            <div class="m-5">
              <p class="text-left text-gray-600 mb-5">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe
                ullam distinctio exercitationem, ipsa illum a nam corrupti
                debitis accusamus veritatis dolore sint repellat eum ab tenetur
                neque dignissimos amet excepturi?
              </p>
              <h2 class="text-left text-lg font-semibold">
                - {{ user.name.first }} {{ user.name.last }}
              </h2>
              <div class="flex">
                <svg
                  v-for="n in rating"
                  :key="n"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  class="w-6 h-6 fill-yellow-400"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.006 5.404.434c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.434 2.082-5.005Z"
                    clip-rule="evenodd"
                  />
                </svg>
              </div>
            </div>
          </div>
        </slide>

        <template #addons>
          <navigation />
          <pagination />
        </template>
      </carousel>
    </div>
  </main>
</template>

<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

const users = ref("");

onMounted(() => {
  fetchUsers();
});

function fetchUsers() {
  axios
    .get("https://randomuser.me/api/?results=10")
    .then((response) => {
      users.value = response.data.results;
      console.log(users.value);
    })
    .catch((err) => {
      console.log(err);
    });
}

const rating = ref(3);
</script>

<script>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

export default {
  name: "App",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
};
</script>
