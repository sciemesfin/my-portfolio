<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <Disclosure as="nav" class="bg-white fixed w-[100%] z-10" v-slot="{ open }">
    <div
      class="mx-auto md:max-w-7xl py-4 justify-center w-[100%] px-2 sm:px-6 lg:px-8"
    >
      <div class="flex justify-between items-center">
        <div>
          <RouterLink to="/" class="flex items-center">
            <img
              class="h-8 w-8 md:h-32 md:w-32 rounded-full"
              src="~/assets/logo.png"
              alt="Workflow"
            />
            <span class="text-[#0065f2] text-2xl font-extrabold pl-3"
              >Mesfin</span
            >
          </RouterLink>
        </div>
        <div class="hidden sm:block">
          <div
            class="items-center md:space-x-8 justify-center justify-items-start md:justify-items-center md:flex md:pt-2 w-full left-0 top-16 px-5 md:px-10 py-3 md:py-0 border-t md:border-t-0"
          >
            <span v-for="(nav, i) in navigation" :key="i">
              <NuxtLink
                :to="nav.href"
                :class="
                  nav.current
                    ? 'flex text-gray-600 cursor-pointer transition-colors duration-300 font-semibold text-blue-600'
                    : 'flex text-gray-600 hover:text-blue-500 cursor-pointer transition-colors duration-300'
                "
              >
                {{ nav.name }}
              </NuxtLink>
            </span>
            <nuxt-link
              href="/resume.pdf"
              class="flex text-gray-600 hover:text-blue-500 cursor-pointer transition-colors duration-300"
              target="_blank"
              >Resume</nuxt-link
            >
          </div>
        </div>
        <div class="flex items-center space-x-5 hidden md:flex">
          <nuxt-link
            href="https://etyopai.com"
            target="_blank"
            class="inline-block shadow-xl rounded-lg bg-blue-600 px-4 py-1.5 text-base font-semibold leading-7 text-white shadow-sm ring-1 ring-blue-600 hover:bg-blue-700 hover:ring-blue-700"
          >
            ChatGPT
            <span class="text-white pl-2" aria-hidden="true">&rarr;</span>
          </nuxt-link>
        </div>
        <div class="right-0 flex items-end sm:hidden">
          <!-- Mobile menu button-->
          <DisclosureButton
            class="inline-flex items-center justify-center rounded-md p-2"
          >
            <span class="sr-only">Open main menu</span>
            <svg
              v-if="!open"
              class="h-6 w-6 text-blue-500"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2.5"
                d="M4 6h16M4 12h16m-7 6h7"
              />
            </svg>
            <svg
              v-else
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </DisclosureButton>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden shadow-md">
      <div class="space-y-1 px-2 pt-2 pb-3">
        <DisclosureButton
          v-for="item in navigation"
          :key="item.name"
          as="a"
          :href="item.href"
          :class="[
            item.current
              ? 'text-blue-600'
              : ' text-gray-600 hover:text-blue-500 cursor-pointer transition-colors duration-300',
            'block px-3 py-2 rounded-md text-base font-medium',
          ]"
          :aria-current="item.current ? 'page' : undefined"
          >{{ item.name }}
        </DisclosureButton>
        <nuxt-link
          href="/resume.pdf"
          class="flex px-3 py-2 text-gray-600 hover:text-blue-500 cursor-pointer transition-colors duration-300"
          target="_blank"
          >Resume</nuxt-link
        >
        <nuxt-link
          href="https://etyopai.com"
          target="_blank"
          className="block w-full font-bold bg-gray-50 px-5 py-3 text-center  text-blue-600 hover:bg-gray-100"
        >
          Try ChatGPT
        </nuxt-link>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";

const navigation = [
  { name: "About me", href: "/about", current: false },
  { name: "Education", href: "/education", current: false },
  { name: "Skills", href: "/skills", current: false },
  { name: "Experiences", href: "/experiences", current: false },
  { name: "Certifications", href: "/certificates", current: false },
  { name: "Projects", href: "/projects", current: false },
  // { name: "Resume", href: "/resume.pdf", current: false }
];
</script>
