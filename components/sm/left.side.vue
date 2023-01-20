<template>
  <div
    class="hidden sm:flex w-full lg:w-3/6 xl:w-2/6 flex flex-col justify-start items-stretch bg-white bg-opacity-80 rounded-md lg:rounded-none lg:rounded-l-md p-3"
  >
    <div class="flex flex-row justify-between items-center mb-4">
      <div class="flex flex-row items-center">
        <nuxt-link
          href="/"
          class="text-blue-600 flex items-center rounded-full cursor-pointer"
          aria-label="Close"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2.5"
            stroke="currentColor"
            class="w-4 h-4"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M9 15L3 9m0 0l6-6M3 9h12a6 6 0 010 12h-3"
            />
          </svg>
          <span class="pl-3">Back to home</span>
        </nuxt-link>
      </div>
      <div class="p-1 rounded-full text-gray-500">
        <button
          class="flex flex-col justify-center items-center p-2 rounded-full focus:ring-2 hover:bg-gray-50 hover:bg-opacity-30 focus:outline-none"
          aria-label="Add"
        >
          <svg class="fill-current h-4 w-4" viewBox="0 0 25 25">
            <path d="M11 11v-11h1v11h11v1h-11v11h-1v-11h-11v-1h11z" />
          </svg>
        </button>
      </div>
    </div>
    <div class="flex-auto flex flex-col">
      <div class="flex-auto flex flex-row">
        <div class="w-full p-1">
          <div class="w-full p-1 flex justify-between">
            <h1 class="font-bold">Saved Conversations</h1>
            <button>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-4 h-4"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0"
                />
              </svg>
            </button>
          </div>
          <ul class="overflow-y-auto max-h-[350px]">
            <li
              v-for="i in 20"
              :key="i"
              class="my-2 p-2 flex flex-row items-center cursor-pointer rounded-lg hover:bg-gray-50 hover:bg-opacity-50"
            >
              <div
                class="bg-gray-200 p-3 w-10 h-10 rounded-full flex items-center justify-center mr-3"
              >
                <svg
                  stroke="currentColor"
                  fill="none"
                  stroke-width="2"
                  viewBox="0 0 24 24"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="h-6 w-6"
                  height="1em"
                  width="1em"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"
                  ></path>
                </svg>
              </div>
              <div class="w-full flex flex-col justify-center">
                <div class="flex flex-row justify-between">
                  <h2 class="text-xs font-bold">Yaeko Lindblom</h2>
                  <div class="text-xs flex flex-row">
                    <span class="text-gray-400"> 10:45 </span>
                  </div>
                </div>
                <div class="flex flex-row justify-between items-center">
                  <p class="text-xs text-gray-500">
                    New the her nor case that lady paid...
                  </p>
                  <span
                    class="text-xs bg-blue-500 rounded-full w-5 h-5 text-center text-white font-bold"
                  >
                    {{ i + 1 }}
                  </span>
                </div>
              </div>
            </li>
          </ul>
          <div class="mt-5">
            <div class="w-full p-1 flex justify-between">
              <h1 class="font-bold">Quick Links</h1>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-4 h-4"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M13.19 8.688a4.5 4.5 0 011.242 7.244l-4.5 4.5a4.5 4.5 0 01-6.364-6.364l1.757-1.757m13.35-.622l1.757-1.757a4.5 4.5 0 00-6.364-6.364l-4.5 4.5a4.5 4.5 0 001.242 7.244"
                />
              </svg>
            </div>
          </div>
          <ul class="overflow-y-auto max-h-[350px]">
            <li v-for="(link, i) in links" :key="i">
              <nuxt-link
                :href="link.href"
                :target="link.newTab?'_blank':'_self'"
                class="my-2 p-2 flex flex-row items-center cursor-pointer rounded-lg hover:bg-gray-50 hover:bg-opacity-50"
              >
                <div class="text-blue-600 mr-3">
                  <div v-html="link.icon"></div>
                </div>
                <div class="w-full flex flex-col justify-center">
                  <h2 class="text-sm font-semibold">{{ link.title }}</h2>
                </div>
              </nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = [
  {
    title: "About the developer",
    href: "/about",
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" />
</svg>
`,
  },
  {
    title: "How to develop?",
    href: "https://beta.openai.com/docs/introduction",
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 12h16.5m-16.5 3.75h16.5M3.75 19.5h16.5M5.625 4.5h12.75a1.875 1.875 0 010 3.75H5.625a1.875 1.875 0 010-3.75z" />
</svg>
`,
    newTab: true,
  },
  {
    title: "API Developer",
    href: "https://beta.openai.com/examples",
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25" />
</svg>
`,
    newTab: true,
  },
  {
    title: "OpenAI Discord",
    href: "https://discord.gg/openai",
    icon: `<svg
          stroke="currentColor"
          fill="currentColor"
          strokeWidth={2}
          viewBox="0 0 640 512"
          class="h-4 w-4"
          height="1em"
          width="1em"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M524.531,69.836a1.5,1.5,0,0,0-.764-.7A485.065,485.065,0,0,0,404.081,32.03a1.816,1.816,0,0,0-1.923.91,337.461,337.461,0,0,0-14.9,30.6,447.848,447.848,0,0,0-134.426,0,309.541,309.541,0,0,0-15.135-30.6,1.89,1.89,0,0,0-1.924-.91A483.689,483.689,0,0,0,116.085,69.137a1.712,1.712,0,0,0-.788.676C39.068,183.651,18.186,294.69,28.43,404.354a2.016,2.016,0,0,0,.765,1.375A487.666,487.666,0,0,0,176.02,479.918a1.9,1.9,0,0,0,2.063-.676A348.2,348.2,0,0,0,208.12,430.4a1.86,1.86,0,0,0-1.019-2.588,321.173,321.173,0,0,1-45.868-21.853,1.885,1.885,0,0,1-.185-3.126c3.082-2.309,6.166-4.711,9.109-7.137a1.819,1.819,0,0,1,1.9-.256c96.229,43.917,200.41,43.917,295.5,0a1.812,1.812,0,0,1,1.924.233c2.944,2.426,6.027,4.851,9.132,7.16a1.884,1.884,0,0,1-.162,3.126,301.407,301.407,0,0,1-45.89,21.83,1.875,1.875,0,0,0-1,2.611,391.055,391.055,0,0,0,30.014,48.815,1.864,1.864,0,0,0,2.063.7A486.048,486.048,0,0,0,610.7,405.729a1.882,1.882,0,0,0,.765-1.352C623.729,277.594,590.933,167.465,524.531,69.836ZM222.491,337.58c-28.972,0-52.844-26.587-52.844-59.239S193.056,219.1,222.491,219.1c29.665,0,53.306,26.82,52.843,59.239C275.334,310.993,251.924,337.58,222.491,337.58Zm195.38,0c-28.971,0-52.843-26.587-52.843-59.239S388.437,219.1,417.871,219.1c29.667,0,53.307,26.82,52.844,59.239C470.715,310.993,447.538,337.58,417.871,337.58Z" />
        </svg>`,
    newTab: true,
  },
  {
    title: "Updates & FAQs",
    href: "https://help.openai.com/en/collections/3742473-chatgpt",
    icon: `<svg
          stroke="currentColor"
          fill="none"
          strokeWidth={2}
          viewBox="0 0 24 24"
          strokeLinecap="round"
          strokeLinejoin="round"
          class="h-4 w-4"
          height="1em"
          width="1em"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6" />
          <polyline points="15 3 21 3 21 9" />
          <line x1={10} y1={14} x2={21} y2={3} />
        </svg>`,
    newTab: true,
  },
];
</script>
