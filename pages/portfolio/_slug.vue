<template>
  
    <article
      class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0 prose lg:prose-xl font-sora"
    >
  
      <img :src="`/images/covers/${article.coverImage}`" class="max-w-full rounded h-auto mt-12 mb-4 shadow-md">
      <h3 class="font-sora text-md font-bold">
              <router-link :to="`/blog/${article.slug}`">
                {{ article.title }}
              </router-link>
            </h3> 
      <nuxt-content :document="article" />
  
      <YoutubeVideo
        v-if="article.youtube"
        :id="article.youtube"
        :title="article.title"
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
      const article = await $content("portfolio", params.slug).fetch();
      const [prev, next] = await $content("portfolio")
        .only(["title", "slug"])
        .sortBy("createdAt", "desc")
        .surround(params.slug)
        .fetch();
      return { article, prev, next };
    },
    components: { YoutubeVideo },
    head () {
    return {
      title: `${this.article.title} - DrmwnSpace`,
      meta: [
        { 
          name: 'author', 
          content: 'Abimanyu Darmawan' 
        },
        {
          name: 'description',
          content: this.article.description
        },
        {
          key: 'og:title',
          property: 'og:title',
          content: `${this.article.title}`,
        },
        {
          key: 'og:image',
          property: 'og:image',
          content: `https://drmwn.space/images/covers/${article.coverImage}`,
        },
        {
          key: 'og:description',
          property: 'og:description',
          content: this.article.description,
        },
        {
          key: 'og:url',
          property: 'og:url',
          content: `https://drmwn.space${this.article.path}`,
        },
        {
          key: 'twitter:title',
          name: 'twitter:title',
          content: `${this.article.title}`,
        },
        
        {
          key: 'twitter:description',
          name: 'twitter:description',
          content: this.article.frase,
        },
        {
          key: 'twitter:creator',
          name: 'twitter:creator',
          content: '@abimanyudrmwn',
        },
        {
          key: 'twitter:card',
          name: 'twitter:card',
          content: 'frase',
        },
        {
          key: 'twitter:image',
          name: 'twitter:image',
          content: `https://drmwn.space${this.article.image}`,
        }
      ]
    }
  },
  };
  </script>
  