<template>
  <div class="h-screen body">
    <div class="h-screen p-5">
      <section
        class="shadow-xl h-full rounded-md w-full lg:w-11/12 lg:mx-auto flex"
      >
        <!-- Left section -->
        <SmLeftSide />
        <!-- Middle section -->
        <div
          class="w-full bg-white h-full lg:flex flex-col justify-start items-stretch border-r-2 border-l-2 border-gray-100 rounded-md sm:rounded-none sm:rounded-r-md"
        >
          <!-- Header with name -->
          <div
            class="flex flex-row items-center justify-between px-3 py-2 bg-gray-50 bg-opacity-40 border-b-2 border-gray-100"
          >
            <div class="">
              <h2 class="font-medium">AI Chatbot</h2>
            </div>
            <div class="flex flex-row">
              <nuxt-link
                href="https://beta.openai.com"
                target="_blank"
                class="p-2 text-blue-600 font-semibold"
                >Create your own chat bot</nuxt-link
              >
            </div>
          </div>
          <!-- Messages -->
          <div
            class="flex-auto flex flex-col justify-between overflow-y-auto p-10"
          >
            <div>
              <input
                v-model="inputValue"
                @input="getData"
                placeholder="Enter your prompt here"
              />
              <div v-if="response">
                <section>
                  Chats:  {{ chats }}
                </section>
              </div>
              <div v-if="loading">Loading...</div>
              <div v-if="error">An error occured: {{ error }}</div>
            </div>
            <div class="flex flex-col">
              <div v-for="i in 1" :key="i">
                <div class="flex flex-row justify-end">
                  <div class="flex items-end">
                    <div
                      class="p-2 text-white bg-blue-600 rounded-full hover:text-gray-200 hover:bg-blue-400 focus:outline-none focus:ring"
                      aria-label="Upload a files"
                    >
                      <svg
                        stroke="currentColor"
                        fill="none"
                        stroke-width="1.5"
                        viewBox="0 0 24 24"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="h-6 w-6"
                        height="1em"
                        width="1em"
                        xmlns="http://www.w3.org/2000/svg"
                      >
                        <path
                          d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"
                        ></path>
                        <circle cx="12" cy="7" r="4"></circle>
                      </svg>
                    </div>
                    <div
                      class="px-4 py-3 rounded-tl-xl rounded-tr-xl rounded-br-xl rounded-none ml-3 my-2 bg-blue-500 text-white"
                    >
                      <p class="text-sm flex">
                        There are many variations of passages of Lorem Ipsum
                      </p>
                      <div class="ml-2 text-xs text-gray-300">
                        <span class="mr-1"> 10:46 </span>
                      </div>
                    </div>
                  </div>
                </div>

                <div class="flex flex-row p-2">
                  <div class="w-full p-2">
                    <div
                      class="bg-gray-100 p-3 rounded-tl-xl rounded-tr-xl rounded-bl-xl mb-2 relative"
                    >
                      <h2 class="text-sm font-semibold mb-2">Yaeko Lindblom</h2>
                      <p class="text-sm">
                        Lorem Ipsum is simply dummy text of the printing and
                        typesetting industry. Lorem Ipsum has been the
                        industry's standard dummy text ever since the 1500s,
                        when an unknown printer took a galley of type and
                        scrambled it to make a type specimen book. It has
                        survived not only five centuries, but also the leap into
                        electronic typesetting, remaining essentially unchanged.
                        It was popularised in the 1960s with the release of
                        Letraset sheets containing Lorem Ipsum passages, and
                        more recently with desktop publishing software like
                        Aldus PageMaker including versions of Lorem Ipsum.
                      </p>
                      <span class="text-xs text-gray-500 bottom-2">09:24</span>
                    </div>
                  </div>

                  <div class="py-2 flex self-end">
                    <div class="text-white bg-green-600 p-1 rounded-full">
                      <svg
                        width="41"
                        height="41"
                        viewBox="0 0 41 41"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                        stroke-width="1.5"
                        class="h-8 w-8"
                      >
                        <path
                          d="M37.5324 16.8707C37.9808 15.5241 38.1363 14.0974 37.9886 12.6859C37.8409 11.2744 37.3934 9.91076 36.676 8.68622C35.6126 6.83404 33.9882 5.3676 32.0373 4.4985C30.0864 3.62941 27.9098 3.40259 25.8215 3.85078C24.8796 2.7893 23.7219 1.94125 22.4257 1.36341C21.1295 0.785575 19.7249 0.491269 18.3058 0.500197C16.1708 0.495044 14.0893 1.16803 12.3614 2.42214C10.6335 3.67624 9.34853 5.44666 8.6917 7.47815C7.30085 7.76286 5.98686 8.3414 4.8377 9.17505C3.68854 10.0087 2.73073 11.0782 2.02839 12.312C0.956464 14.1591 0.498905 16.2988 0.721698 18.4228C0.944492 20.5467 1.83612 22.5449 3.268 24.1293C2.81966 25.4759 2.66413 26.9026 2.81182 28.3141C2.95951 29.7256 3.40701 31.0892 4.12437 32.3138C5.18791 34.1659 6.8123 35.6322 8.76321 36.5013C10.7141 37.3704 12.8907 37.5973 14.9789 37.1492C15.9208 38.2107 17.0786 39.0587 18.3747 39.6366C19.6709 40.2144 21.0755 40.5087 22.4946 40.4998C24.6307 40.5054 26.7133 39.8321 28.4418 38.5772C30.1704 37.3223 31.4556 35.5506 32.1119 33.5179C33.5027 33.2332 34.8167 32.6547 35.9659 31.821C37.115 30.9874 38.0728 29.9178 38.7752 28.684C39.8458 26.8371 40.3023 24.6979 40.0789 22.5748C39.8556 20.4517 38.9639 18.4544 37.5324 16.8707ZM22.4978 37.8849C20.7443 37.8874 19.0459 37.2733 17.6994 36.1501C17.7601 36.117 17.8666 36.0586 17.936 36.0161L25.9004 31.4156C26.1003 31.3019 26.2663 31.137 26.3813 30.9378C26.4964 30.7386 26.5563 30.5124 26.5549 30.2825V19.0542L29.9213 20.998C29.9389 21.0068 29.9541 21.0198 29.9656 21.0359C29.977 21.052 29.9842 21.0707 29.9867 21.0902V30.3889C29.9842 32.375 29.1946 34.2791 27.7909 35.6841C26.3872 37.0892 24.4838 37.8806 22.4978 37.8849ZM6.39227 31.0064C5.51397 29.4888 5.19742 27.7107 5.49804 25.9832C5.55718 26.0187 5.66048 26.0818 5.73461 26.1244L13.699 30.7248C13.8975 30.8408 14.1233 30.902 14.3532 30.902C14.583 30.902 14.8088 30.8408 15.0073 30.7248L24.731 25.1103V28.9979C24.7321 29.0177 24.7283 29.0376 24.7199 29.0556C24.7115 29.0736 24.6988 29.0893 24.6829 29.1012L16.6317 33.7497C14.9096 34.7416 12.8643 35.0097 10.9447 34.4954C9.02506 33.9811 7.38785 32.7263 6.39227 31.0064ZM4.29707 13.6194C5.17156 12.0998 6.55279 10.9364 8.19885 10.3327C8.19885 10.4013 8.19491 10.5228 8.19491 10.6071V19.808C8.19351 20.0378 8.25334 20.2638 8.36823 20.4629C8.48312 20.6619 8.64893 20.8267 8.84863 20.9404L18.5723 26.5542L15.206 28.4979C15.1894 28.5089 15.1703 28.5155 15.1505 28.5173C15.1307 28.5191 15.1107 28.516 15.0924 28.5082L7.04046 23.8557C5.32135 22.8601 4.06716 21.2235 3.55289 19.3046C3.03862 17.3858 3.30624 15.3413 4.29707 13.6194ZM31.955 20.0556L22.2312 14.4411L25.5976 12.4981C25.6142 12.4872 25.6333 12.4805 25.6531 12.4787C25.6729 12.4769 25.6928 12.4801 25.7111 12.4879L33.7631 17.1364C34.9967 17.849 36.0017 18.8982 36.6606 20.1613C37.3194 21.4244 37.6047 22.849 37.4832 24.2684C37.3617 25.6878 36.8382 27.0432 35.9743 28.1759C35.1103 29.3086 33.9415 30.1717 32.6047 30.6641C32.6047 30.5947 32.6047 30.4733 32.6047 30.3889V21.188C32.6066 20.9586 32.5474 20.7328 32.4332 20.5338C32.319 20.3348 32.154 20.1698 31.955 20.0556ZM35.3055 15.0128C35.2464 14.9765 35.1431 14.9142 35.069 14.8717L27.1045 10.2712C26.906 10.1554 26.6803 10.0943 26.4504 10.0943C26.2206 10.0943 25.9948 10.1554 25.7963 10.2712L16.0726 15.8858V11.9982C16.0715 11.9783 16.0753 11.9585 16.0837 11.9405C16.0921 11.9225 16.1048 11.9068 16.1207 11.8949L24.1719 7.25025C25.4053 6.53903 26.8158 6.19376 28.2383 6.25482C29.6608 6.31589 31.0364 6.78077 32.2044 7.59508C33.3723 8.40939 34.2842 9.53945 34.8334 10.8531C35.3826 12.1667 35.5464 13.6095 35.3055 15.0128ZM14.2424 21.9419L10.8752 19.9981C10.8576 19.9893 10.8423 19.9763 10.8309 19.9602C10.8195 19.9441 10.8122 19.9254 10.8098 19.9058V10.6071C10.8107 9.18295 11.2173 7.78848 11.9819 6.58696C12.7466 5.38544 13.8377 4.42659 15.1275 3.82264C16.4173 3.21869 17.8524 2.99464 19.2649 3.1767C20.6775 3.35876 22.0089 3.93941 23.1034 4.85067C23.0427 4.88379 22.937 4.94215 22.8668 4.98473L14.9024 9.58517C14.7025 9.69878 14.5366 9.86356 14.4215 10.0626C14.3065 10.2616 14.2466 10.4877 14.2479 10.7175L14.2424 21.9419ZM16.071 17.9991L20.4018 15.4978L24.7325 17.9975V22.9985L20.4018 25.4983L16.071 22.9985V17.9991Z"
                          fill="currentColor"
                        ></path>
                      </svg>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- Input for writing a messages -->
          <div class="flex flex-row justify-between items-center p-3">
            <div class="">
              <nuxt-link
                href="/about"
                type="button"
                class="p-2 text-white bg-blue-600 rounded-full hover:text-gray-200 hover:bg-blue-400 focus:outline-none focus:ring"
                aria-label="Upload a files"
              >
                <svg
                  stroke="currentColor"
                  fill="none"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="h-6 w-6"
                  height="1em"
                  width="1em"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
                  <circle cx="12" cy="7" r="4"></circle>
                </svg>
              </nuxt-link>
            </div>
            <div class="flex-1 px-3">
              <div class="flex items-between">
                <div
                  class="rounded-md p-1 shadow w-full flex justify-between px-4 bg-white"
                >
                  <textarea
                    rows="1"
                    class="bg-white overflow-hidden resize-none text-gray-900 text-sm w-full py-2 border-none focus:ring-0 focus:outline-none focus:outline-none"
                    v-model="inputValue"
                    @keyup.enter="getData"
                  />
                  <button
                    class="relative rounded-md text-gray-500 right-0 hover:bg-gray-100 dark:hover:text-gray-400 dark:hover:bg-gray-900 disabled:hover:bg-transparent dark:disabled:hover:bg-transparent"
                    @click="getData"
                  >
                    <svg
                      stroke="currentColor"
                      fill="currentColor"
                      stroke-width="0"
                      viewBox="0 0 20 20"
                      class="h-4 w-4 rotate-90"
                      height="1em"
                      width="1em"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 001.169 1.409l5-1.429A1 1 0 009 15.571V11a1 1 0 112 0v4.571a1 1 0 00.725.962l5 1.428a1 1 0 001.17-1.408l-7-14z"
                      ></path>
                    </svg>
                  </button>
                </div>
              </div>
            </div>
            <div class="flex flex-row">
              <button
                type="button"
                class="p-2 text-gray-400 rounded-full hover:text-gray-600 hover:bg-gray-100 focus:outline-none focus:ring"
                aria-label="Show emojis"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  class="w-6 h-6"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M16.023 9.348h4.992v-.001M2.985 19.644v-4.992m0 0h4.992m-4.993 0l3.181 3.183a8.25 8.25 0 0013.803-3.7M4.031 9.865a8.25 8.25 0 0113.803-3.7l3.181 3.182m0-4.991v4.99"
                  />
                </svg>
              </button>
              <button
                type="button"
                class="p-2 ml-2 text-white bg-blue-600 rounded-full hover:text-gray-600 hover:bg-gray-100 focus:outline-none focus:ring"
                aria-label="Record a voice"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  class="w-6 h-6"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M17.593 3.322c1.1.128 1.907 1.077 1.907 2.185V21L12 17.25 4.5 21V5.507c0-1.108.806-2.057 1.907-2.185a48.507 48.507 0 0111.186 0z"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const inputValue = ref("");
    const response = ref(null);
    const error = ref(null);
    const loading = ref(false);
    const chats=ref(null)

    const getData = async () => {
      loading.value = true;
      error.value = null;
      try {
        const apiKey = '';
        const res = await fetch(
          "https://api.openai.com/v1/completions",
          {
            method: "POST",
            headers: {
              "Content-Type": "application/json",
              Authorization: `Bearer ${apiKey}`,
            },
            body: JSON.stringify({
              prompt: inputValue.value,
              model: "text-davinci-003",
              temperature: 0.9,
              max_tokens: 2000,
              top_p: 1,
              frequency_penalty: 0.0,
              presence_penalty: 0.6,
              stop: [" Human:", " AI:"],
            }),
          }
        );
        const data = await res.json();
        response.value = data.choices[0].text;
        chats.value=[...chats.value,...[{q:inputValue.value,a:data.choices[0].text}]]
      } catch (err) {
        error.value = err;
      } finally {
        loading.value = false;
      }
    };

    return {
      inputValue,
      response,
      chats,
      loading,
      error,
      getData,
    };
  },
};
</script>

<style>
.body {
  background: url("https://i.redd.it/iibrptucse951.png");
  background-repeat: no-repeat;
  background-size: cover;
}

section {
  height: 80vh;
}

.search-input {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 20 20'%3e%3cpath stroke='%239ca3af' d='M18.109,17.776l-3.082-3.081c-0.059-0.059-0.135-0.077-0.211-0.087c1.373-1.38,2.221-3.28,2.221-5.379c0-4.212-3.414-7.626-7.625-7.626c-4.212,0-7.626,3.414-7.626,7.626s3.414,7.627,7.626,7.627c1.918,0,3.665-0.713,5.004-1.882c0.006,0.085,0.033,0.17,0.098,0.234l3.082,3.081c0.143,0.142,0.371,0.142,0.514,0C18.25,18.148,18.25,17.918,18.109,17.776zM9.412,16.13c-3.811,0-6.9-3.089-6.9-6.9c0-3.81,3.089-6.899,6.9-6.899c3.811,0,6.901,3.09,6.901,6.899C16.312,13.041,13.223,16.13,9.412,16.13z'/%3e%3c/svg%3e");
  background-repeat: no-repeat;
  background-position: left 0.75rem center;
  background-size: 0.9rem 1.25rem;
}
</style>
