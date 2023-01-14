<template>
  <div class="bg-gray-900">
    <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
  <h2 class="text-2xl font-bold font-sora mb-10">{{title}}</h2>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
    <div v-for="article in current" :key="article.slug" class="border border-gray-100 rounded-xl shadow-lg">
          <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
            <router-link :to="`/blog/${article.slug}`">
              <img alt="Article Image" class="lazyLoad isLoaded object-scale-down" :src="`/images/covers/${article.coverImage}`">
            </router-link>
          </div>
          <div class="p-3 pr-2"><div class="h-2"></div> 
          <span class="text-xs text-gray-600">{{ formatDate(article.date) }}</span>
          <h2 class="font-sora text-md font-bold">
            <router-link :to="`/blog/${article.slug}`">
              {{ article.title }}
            </router-link>
          </h2> 
          <div class="h-2"></div> 
            <p class="font-sora text-md font-light text-gray-600 leading-5">
              {{ article.frase.substring(0,64)+"..." }}
              </p> 
          <div class="h-6">
          </div> 
          <div class="flex justify-between items-end">
            <span class="bg-green-50 text-green-600 px-4 py-2 rounded-full text-sm font-sora">{{ article.category }}</span> 
            <a class="hover:bg-gray-100 px-4 py-2 rounded-full text-md"><router-link :to="`/blog/${article.slug}`">Read More →&#xFEFF;</router-link></a>
          </div>
        </div>
      </div>
      </div>
    </div>
</div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("blog", params.slug)
      .sortBy("date", "desc")
      .fetch();

    const all = articles.map((e) => e.category);
    const categories = [...new Set(all)];

    const title = "Newest Article";
    const current = articles;
    return {
      articles,
      categories,
      title,
      current,
    };
  },
  head: {
    title: 'Blog - DrmwnSpace',
    meta: [
      { 
        name: 'author', 
        content: 'Abimanyu Darmawan' 
      },
      {
        name: 'description',
        content: 'Sharing about Web Development Technology, Game Development and more!',
      },
      {
        key: 'og:title',
        property: 'og:title',
        content: 'Blog - DrmwnSpace',
      },
      {
        key: 'og:description',
        property: 'og:description',
        content: 'Sharing about Web Development Technology, Game Development and more!',
      },
      { 
        hid: 'og:image', 
        property: 'og:image', 
        content: 'https://res.cloudinary.com/belanga/image/upload/v1650919422/drmwnicon-01_spqbmw.jpg',
      },
      {
        key: 'og:url',
        property: 'og:url',
        content: 'https://drmwn.space/blog',
      },
      {
        key: 'twitter:title',
        name: 'twitter:title',
        content: 'Blog - DrmwnSpace',
      },
      {
        key: 'twitter:card',
        name: 'twitter:card',
        content: 'summary',
      },
      {
        key: 'twitter:creator',
        name: 'twitter:creator',
        content: '@abimanyudrmwn',
      },
      {
        key: 'twitter:description',
        name: 'twitter:description',
        content: 'Sharing about Web Development Technology, Game Development and more!',
      }
    ]
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },
    reset() {
      this.title = "Newest Article";
      this.current = this.articles;
    },
    filter(value) {
      this.title = value;
      this.current = this.articles.filter((e) => e.category == value);
    },
  },
  
};
</script>