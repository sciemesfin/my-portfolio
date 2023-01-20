<template>
  <div>
    <div class="w-full hidden sm:block">
   <sm-chat-ui/>
  </div>
  <div class="w-full sm:hidden">
   <xs-chat-ui/>
  </div>
  </div>
</template>
<script setup>
import smChatUi from '~~/components/sm/sm.chat.ui.vue';
// import axios from 'axios'


// const { pending, data: posts } = useLazyFetch('https://randomuser.me/api/')
// const data=axios.post("asdfg/asdf")
// console.log("API DATA",data)
// watch(posts, (newPosts) => {
//   // Because posts starts out null, you will not have access
//   // to its contents immediately, but you can watch it.
// })

definePageMeta({
  layout: "secondary",
});

</script>