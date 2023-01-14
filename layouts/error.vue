// layouts/error.vue
<template>
  <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
      <div class="flex flex-col items-center">
        <div class="h-16"></div>
        <img src="../static/images/404error.svg" alt="404 Error" class="h-64">
        <h2 class="text-2xl font-light font-sora" v-if="error.statusCode === 404"> Page not found</h2>
        <h2 class="text-2xl font-light font-sora" v-else> An error occurred</h2>
        <NuxtLink to="/" class="underline">Back to Home</NuxtLink>
        <div class="h-2 w-20 bg-gray-100 rounded-full mt-3"></div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'error',
  props: {
    error: {
      type: Object,
    },
  },
};
</script>