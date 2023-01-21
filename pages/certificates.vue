<template>
  <div class="pt-20 md:pt-32">
    <div
      class="mx-auto md:max-w-7xl py-10 justify-center w-[100%] px-5 sm:px-6 lg:px-8 pb-64"
    >
    <h1 class="text-xl my-8 text-center md:text-7xl font-extrabold py-2">Certicates & Awards</h1>
      <div class="md:flex md:flex-wrap h-full">
        <div
          v-for="item in items"
          :key="item.school"
          class="w-full p-2 md:p-10 md:w-1/2"
        >
          <div  class="h-full max-h-[305px] md:max-h-[550px] cursor-pointer bg-white shadow-md border border-gray-200 rounded-lg">
            <img
              :src="item.image"
              alt=""
              class="object-contain h-full max-h-[300px] md:max-h-[548px]"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import udacity from "../assets/udacity.png";
import ibm from "../assets/ibm.png";
import google from "../assets/google.png";
import php from "../assets/php.png";
import cs1 from "../assets/award.jpeg";
import cs2 from "../assets/cs2.jpeg";
const items = [
  {
    title: "AWS Machine Learning Foundations 2022",
    school: "Udacity",
    image: udacity,
  },
  {
    title: "Mobile Application Developer Mastery Award",
    school: "IBM",
    image: ibm,
  },
  {
    title: "Google Digital Marketing",
    school: "Google",
    image: google,
  },
  {
    title: "Top 25% Laravel Developer",
    school: "TestDome",
    image: php,
  },
  {
    title: "Certificate of Award",
    school: "Addis Ababa University",
    image: cs1,
  },
  {
    title: "Certificate of Appriciation",
    school: "Addis Ababa University",
    image: cs2,
  },
];
</script>

<style></style>
