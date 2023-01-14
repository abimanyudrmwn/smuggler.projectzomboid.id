<template>
  <section class="bg-gray-900 py-3">
    <article class=" mx-auto max-w-5xl tracking-wide px-6 xl:px-0 font-sora">

      <h3 class="py-6 text-white font-sora lg:text-2xl text-1xl font-bold">{{ article.title }}</h3> 

      <div class="prose lg:prose-xl justify">

        <nuxt-content :document="article" />

        <YoutubeVideo
          v-if="article.youtube"
          :id="article.youtube" 
          :title="article.title"
        />
      </div>
  </article>
  </section>

</template>

<script>
import YoutubeVideo from "../../components/global/YoutubeVideo.vue";
export default {
  async asyncData({ $content, params }) {
    const article = await $content("wiki", params.slug).fetch();
    const [prev, next] = await $content("wiki")
      .only(["title", "slug"])
      .sortBy("createdAt", "desc")
      .surround(params.slug)
      .fetch();
    return { article, prev, next };
  },
  components: { YoutubeVideo },
};
</script>
