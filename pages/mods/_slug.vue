<template>
  
    <article
      class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0 prose lg:prose-xl font-sora"
    >
  
      <img :src="`/images/covers/${mods.coverImage}`" class="max-w-full rounded h-auto mt-12 mb-4 shadow-md">
      <h3 class="font-sora text-md font-bold">
              <router-link :to="`/blog/${mods.slug}`">
                {{ mods.title }}
              </router-link>
            </h3> 
      <nuxt-content :document="mods" />
  
      <YoutubeVideo
        v-if="mods.youtube"
        :id="mods.youtube"
        :title="mods.title"
      />
      <div class="mt-6 mb-4 p-1 text-white bg-gray-100 rounded-full"></div> 
      <footer class="py-10 px-5 text-center mx-auto max-w-5xl">
        <span class="font-sora font-md text-md my-6">
              <a class="text-gray-900"><router-link to="/blog">Back to Blog Home</router-link></a>
            </span>
        <p class="mt-6 text-sm text-gray-500">©2022 DrmwnSpace - Build with Vue + Nuxt ❤️ Tailwind CSS</p>
      </footer>
  
    </article>
  </template>
  
  <script>
  import YoutubeVideo from "../../components/global/YoutubeVideo.vue";
  export default {
    async asyncData({ $content, params }) {
      const mods = await $content("mods", params.slug).fetch();
      const [prev, next] = await $content("mods")
        .only(["title", "slug"])
        .sortBy("createdAt", "desc")
        .surround(params.slug)
        .fetch();
      return { mods, prev, next };
    },
    async fetch() {
    const { data } = await this.$axios.get(
      `api_url`
    );
    this.mods = data.response.results[0];
    this.loading = false;
  },
  data() {
    return {
      mods: {},
    };
  },
  head() {
    return {
      title: this.mods.title ? `${this.mods.title}` : "",
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.mods.frase,
        },
        { hid: "og-title", property: "og:title", content: this.mods.title },
        {
          hid: "og-image",
          property: "og:image",
          content: this.mods.coverImage,
        },
        { hid: "og-image-width", property: "og:image:width", content: 500 },
        { hid: "og-image-height", property: "og:image:height", content: 300 },
        {
          hid: "og-image-type",
          property: "og:image:type",
          content: "image/jpeg",
        },
      ],
      link: [{ rel: 'icon', type: 'image/x-icon', href: 'https://www.projectzomboid.id/assets/favicon.png' }],
    };
  },
    components: { YoutubeVideo },
  };
  </script>
  