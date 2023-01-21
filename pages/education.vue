<template>
  <div class="pt-20 md:pt-32">
    <div
      class="mx-auto md:max-w-7xl py-4 justify-center w-[100%] px-5 sm:px-6 lg:px-8 pb-64"
    >
      <h1 class="text-xl my-8 text-center md:text-7xl font-extrabold py-2">
        Education
      </h1>
      <div class="md:flex md:space-x-10 h-[100vh]">
        <section v-for="(item, i) in items" :key="i" class="w-full md:w-1/2">
          <div class="p-10">
            <div class="">
              <img :src="item.logo" alt="" class="max-w-64 max-h-64" />
              <div>
                <h1 class="font-extrabold text-xl md:text-6xl">
                  {{ item.degree }}
                </h1>
                <div class="py-4">
                  <nuxt-link
                    href="https://www.aau.edu.et"
                    target="_blank"
                    class="font-bold text-blue-600 text-2xl"
                    >{{ item.school }}</nuxt-link
                  >
                </div>
                <p>{{ item.duration }}</p>
              </div>
            </div>
          </div>
        </section>
        <section class="w-full md:w-1/2">
          <img src="~/assets/degree.jpeg" alt="" class="w-full h-full" />
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const items = [
  {
    school: "Addis Ababa University",
    location: "Addis Ababa, Ethiopia",
    duration: "September 2014 - Junly 2018",
    degree: "Bachelor of Science Degree in Computer Science",
    logo: "https://oia.osu.edu/media/ggyjd1tj/aau2.jpg",
  },
];
</script>

<style></style>
