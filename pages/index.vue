<template>
  <div class="pt-20 md:pt-32">
    <section class="bg-white dark:bg-gray-900">
      <div
        class="gap-16 items-center py-8 px-4 mx-auto max-w-screen-xl lg:grid lg:grid-cols-2 lg:py-16 lg:px-6"
      >
        <div class="font-light text-gray-500 sm:text-lg dark:text-gray-400">
          <h2
            class="mb-4 text-4xl md:text-5xl text-blue-600 font-extrabold dark:text-white"
          >
            Created a powerful Chatbot for AI lovers
          </h2>
          <p class="mb-4">
            After testing the OpenAI ChatGPT bot, I can't wait to make AI
            enabled services available in Africa. Thanks to OpenAI for providing
            open API endpounts, I am able to create a simple AI powered chat-bot
            by utilizing the OpenAI Chat API endpoint.
          </p>
          <p>
            This technology enables developers to create interactive, natural
            language-based conversations with users. This is the simplest
            alternative to ChatGPT (Optimizing language models for dialogue)
          </p>
          <div class="py-5">
            <nuxt-link
              href="/chat"
              class="inline-flex items-center justify-center px-5 py-3 mr-3 text-base font-medium text-center text-white rounded-lg bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-900"
            >
              Get started
              <svg
                class="w-5 h-5 ml-2 -mr-1"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
            </nuxt-link>
            <nuxt-link
              href="https://www.linkedin.com/in/mesfin-tsegaye"
              target="_blank"
              class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-gray-900 border border-gray-300 rounded-lg hover:bg-gray-100 focus:ring-4 focus:ring-gray-100 dark:text-white dark:border-gray-700 dark:hover:bg-gray-700 dark:focus:ring-gray-800"
            >
              Speak to Mesfin
            </nuxt-link>
          </div>
        </div>
        <div class="grid grid-cols-2 gap-4 mt-8">
          <img
            class="w-full rounded-lg"
            src="~/assets/i2.avif"
            alt="office content 1"
          />
          <img
            class="mt-4 w-full lg:mt-10 rounded-lg"
            src="~/assets/i3.avif"
            alt="office content 2"
          />
        </div>
      </div>
    </section>

    <section>
      <div class="md:max-w-7xl justify-center w-[100%] py-4 px-4 mt-6 mx-auto">
        <div class="md:max-w-[80%] mx-auto">
          <h1 class="text-2xl font-sans md:text-6xl font-extrabold text-center">
            Building next-gen apps with OpenAI’s powerful models
          </h1>
          <p class="py-4 text-center text-gray-600 text-lg md:text-xl">
            The OpenAI API can be applied to virtually any task that involves
            understanding or generating natural language or code. We offer a
            spectrum of models with different levels of power suitable for
            different tasks, as well as the ability to fine-tune your own custom
            models. These models can be used for everything from content
            generation to semantic search and classification.
          </p>
        </div>
      </div>
    </section>

    <section>
      <div class="md:max-w-7xl w-[100%] py-4 px-4 mt-6 mx-auto">
        <div class="md:flex md:space-x-6 justify-between">
          <div
            v-for="(item, i) in serviceList"
            :key="i"
            class="cursor-pointer py-3"
          >
            <div
              class="max-w-sm h-full rounded-xl overflow-hidden shadow-xl border border-gray-100"
            >
              <nuxt-link :href="item.route" target="_blank">
                <img
                class="w-full h-32"
                :src="item.img"
                alt="Sunset in the mountains"
              />
              <div class="px-6 py-4">
                <div class="font-bold text-xl mb-2">{{ item.title }}</div>
                <p class="text-gray-700 text-base">
                  {{ item.desc }}
                </p>
              </div>
              </nuxt-link>
            </div>
          </div>
        </div>
        <div class="flex justify-center mt-6">
          <nuxt-link
            href="https://beta.openai.com/examples"
            target="_blank"
            class="inline-block shadow-xl rounded-lg bg-blue-600 px-4 py-2.5 text-base font-semibold leading-7 text-white shadow-sm ring-1 ring-blue-600 hover:bg-blue-700 hover:ring-blue-700"
          >
            See more examples
            <span class="text-blue-200 pl-2" aria-hidden="true">&rarr;</span>
          </nuxt-link>
        </div>
      </div>
    </section>

    <section class="bg-[#edf2f7] mt-16 py-6">
      <div class="md:max-w-7xl justify-center w-[100%] py-4 px-4 mt-6 mx-auto">
        <div class="md:max-w-[70%] mx-auto">
          <h2 class="text-lg text-blue-600 font-semibold py-2 text-center">
            Ready?
          </h2>
          <h1 class="text-2xl font-sans md:text-6xl font-extrabold text-center">
            Try it, 100% free
          </h1>
        </div>
        <div class="py-10 flex justify-center">
          <RouterLink
            to="/chat"
            class="inline-block shadow-xl my-3 rounded-lg bg-blue-600 px-6 py-2.5 text-base font-semibold leading-7 text-white shadow-sm ring-1 ring-blue-600 hover:bg-blue-700 hover:ring-blue-700"
          >
            Try ChatGPT
          </RouterLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const serviceList = [
  {
    img: "https://img.freepik.com/free-vector/data-centers-are-data-centers-serve-applications-supporting-business-information-cloud-computing-technology-business-analysis-analytics-research-strategy-statistic-planning-marketing_1150-55220.jpg?w=1800&t=st=1668960417~exp=1668961017~hmac=6478baa595c5d0f38e90fcbb7c02296afa0eeaf9626cfe98e2f133373988b45b",
    title: "Text completion",
    desc: "It provides a simple but powerful interface to any of our models",
    route: "https://beta.openai.com/docs/guides/completion",
  },
  {
    img: "https://kinsta.com/de/wp-content/uploads/sites/5/2019/11/woocommerce-crm-1024x512.png",
    title: "Image generation",
    desc: "The image generations endpoint allows you to create an original image given a text prompt",
    route: "https://beta.openai.com/docs/guides/images",
  },
  {
    img: "https://img.freepik.com/free-vector/female-student-listening-webinar-online_74855-6461.jpg?w=2000&t=st=1668960950~exp=1668961550~hmac=6747921465eda3ea30df84ea43e07264e44786a77d0d3c07bb70b5e691d59d0d",
    title: "Code Compilation",
    desc: "Use the GPT-3 series Codex model series for your coding projects.",
    route: "https://beta.openai.com/docs/guides/code",
  },
  {
    img: "https://img.freepik.com/free-vector/gradient-api-illustration_23-2149373204.jpg?w=2000&t=st=1668961150~exp=1668961750~hmac=0a7ec352a5c8ec3e13ce1335f88220276537fd16b0ef172d7cf3d9ec8f2198cb",
    title: "Embedding",
    desc: "OpenAI’s text embeddings measure the relatedness of text strings. ",
    route: "https://beta.openai.com/docs/guides/embeddings",
  },
];
</script>

<style>
.line-clamp {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
