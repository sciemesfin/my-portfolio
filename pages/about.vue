<template>
  <div class="pt-20 md:pt-32 h-full">
    <div
      class="mx-auto md:max-w-7xl h-full w-[100%] px-2 py-10 sm:px-6 lg:px-8"
    >
      <div class="md:flex justify-between">
        <section class="w-full md:w-1/2">
          <h1 class="text-4xl my-8 md:mb-10 md:text-7xl font-extrabold py-2">
            Mesfin Tsegaye
          </h1>
          <p class="text-gray-500">
            Professional Software Engineer with 5 years of commercial experience
            as a Full stack developer, Frontend Developer, backend Developer,
            Mobile app developer, in Problem Solving, and APIs developer and
            integrations. I have worked on the development of problem solving
            projects for the Education sectors, Financial industries,
            E-Commerce, Transportation sectors, and Garment and Fashion
            industries. I love Programming; studying real world problems and
            looking for a better solution.
          </p>
          <div class="flex flex-wrap py-1" v-for="item in items" :key="item.title">
            <p>{{ item.title }}:</p>
            <nuxt-link :href="item.href" target="_blank" class="pl-3 md:pl-5 text-blue-600"
              >{{ item.value }}
            </nuxt-link>
          </div>
        </section>
        <section class="my-3">
          <img
            src="~/assets/mesfin.png"
            alt="mesfin"
            class="h-full max-h-[500px] w-full object-contain"
          />
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const items = [
  {
    title: "Address",
    value: "Addis Ababa, Ethiopia",
    href: "https://en.wikipedia.org/wiki/Addis_Ababa",
  },
  {
    title: "Linkedin",
    value: "mesfin-tsegaye",
    href: "https://www.linkedin.com/in/mesfin-tsegaye",
  },
  {
    title:"Github",
    value:"@sciemesfin",
    href:"https://github.com/sciemesfin"
  },
  {
    title:"Email",
    value:"sciemesfin55@gmail.com",
    hrfe:'mailto:sciemesfin55@gmail.com'
  },
  {
    title:"Phone Number",
    value:"+251 91 152 2902",
    href:"tel:+251911522902"
  }
];
</script>
