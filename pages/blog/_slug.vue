<template>
  
  <article class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0 font-sora">
    <nav class="rounded-md w-full mt-6 mb-4">
      <ol class="list-reset flex">
        <li><a class="font-sora text-blue-600 hover:text-blue-700"><router-link to="/">Home</router-link></a></li>
        <li><span class="text-gray-500 mx-2 font-sora">/</span></li>
        <li class="font-sora text-blue-600 hover:text-blue-700"><router-link to="/blog">Blog</router-link></li>
        <li><span class="text-gray-500 mx-2 font-sora">/</span></li>
        <li><span class="text-gray-500 mx-2 font-sora">{{  article.title.substring(0,18)+"..."  }}</span></li>
      </ol>
    </nav>

    <h3 class="font-sora lg:text-5xl text-2xl font-bold">{{ article.title }}</h3> 
    <img :src="`/images/covers/${article.coverImage}`" class="max-w-full rounded h-auto mt-6 mb-6 shadow-md"/>

    <div class="prose lg:prose-xl justify">

      <nuxt-content :document="article" />

      <YoutubeVideo
        v-if="article.youtube"
        :id="article.youtube" 
        :title="article.title"
      />
    </div>

    <div class="mt-6 mb-4 p-1 text-white bg-gray-100 rounded-full"></div> 
    <footer class="py-10 px-5 text-center mx-auto max-w-5xl">
      <span class="font-sora font-md text-md my-6">
            <a class="text-gray-900"><router-link to="/blog">Back to Blog Home</router-link></a>
          </span>
      <p class="font-sora mt-6 text-sm text-gray-500">©2022 DrmwnSpace - Build with Vue + Nuxt ❤️ Tailwind CSS</p>
    </footer>

  </article>
</template>

<script>
import YoutubeVideo from "../../components/global/YoutubeVideo.vue";
export default {
  async asyncData({ $content, params }) {
    const article = await $content("blog", params.slug).fetch();
    const [prev, next] = await $content("blog")
      .only(["title", "slug"])
      .sortBy("createdAt", "desc")
      .surround(params.slug)
      .fetch();
    return { article, prev, next };
  },
  components: { YoutubeVideo },
};
</script>
