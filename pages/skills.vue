<template>
  <div class="pt-20 md:pt-32">
    <div
      class="mx-auto md:max-w-7xl py-10 justify-center w-[100%] px-5 sm:px-6 lg:px-8"
    >
    <h1 class="text-xl my-8 text-center md:text-7xl font-extrabold py-2">Skills</h1>
      <div class="md:flex md:space-x-3 md:py-10 md:space-x-20">
        <section class="w-full md:w-1/2 md:px-10">
          <div>
            <div class="py-2 text-xl md:text-2xl font-semibold">
            Top technologies
          </div>
          <div
            v-for="item in topStacks"
            :key="item.title"
            class="flex items-center justify-between py-2 md:ml-5"
          >
            <div class="text-sm">{{ item.title }}</div>
            <div class="text-sm">{{ item.year }} years experience</div>
          </div>
          </div>

          <div class="py-2 text-xl md:text-2xl font-semibold mt-3">
            Languages
          </div>
          <div class="flex space-x-3">
            <div v-for="item in languages" :key="item" class="">
              <div
                class="border border-green-100 bg-green-100 rounded-full w-full p-1 px-4"
              >
                <p class="text-center text-sm">
                  {{ item }}
                </p>
              </div>
            </div>
          </div>
        </section>
        <section class="w-full md:border-l py-5 md:px-10">
          <div v-for="item in skills" :key="item.title" class="pb-10">
            <div class="py-2 text-xl md:text-2xl font-semibold">
              {{ item.title }}
            </div>
            <div class="flex flex-wrap">
              <div v-for="skill in item.items" :key="skill" class="my-2 mx-3">
                <div
                  class="border border-green-100 bg-green-100 rounded-full w-full p-1 px-4"
                >
                  <p class="text-center text-sm">
                    {{ skill }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const topStacks = [
  { title: "React", year: 5 },
  { title: "Vue", year: 5 },
  { title: "Node js", year: 5 },
  { title: "Next js", year: 3 },
  { title: "Nuxt js", year: 4 },
  { title: "PHP", year: 5 },
  { title: "TypeScript", year: 3 },
  { title: "JavaScript", year: 6 },
];

const languages = ["English", "Amharic", "Afan Oromo"];

const skills = [
  {
    title: "Technologies",
    items: [
      "TypeScript",
      "JavaScript",
      "React",
      "React Native",
      "Next js",
      "Vue",
      "Nuxt js",
      "Node js",
      "PHP",
      "Laravel",
      "MySQL",
      "PostgreSQL",
      "MariaDB",
      "MongoDB",
      "DynamoDB",
      "Flutter",
      "Dart",
      "Swift",
      "Android",
      "AWS",
      "GCP",
      "Git",
      "CI/CD",
      "Solidity",
      "Loopback",
      "Strapi",
      "Koa",
      "Express js",
      "Firebase",
      "GraphQL",
      "Supabase",
      "Python",
      "Django",
      "Frappe",
      "Scrum",
      "Kanban",
    ],
  },
];
</script>
