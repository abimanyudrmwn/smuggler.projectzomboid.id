<template>
  <section class="bg-gray-900">
  <div class="py-8 px-4 mx-auto max-w-screen-xl lg:py-16 lg:px-6">
      <div class="mx-auto max-w-screen-sm text-center lg:mb-16 mb-8">
          <h2 class="mb-4 text-3xl lg:text-4xl tracking-tight font-sora text-white">Wiki</h2>
          <p class="font-sora text-gray-400 sm:text-xl">Anything about mods that Indonesia Project Zomboid Community create.</p>
      </div> 
      <div class="grid gap-8 lg:grid-cols-2">
          <article  v-for="article in current" :key="article.slug" class="p-6 bg-gray-900 rounded-lg border border-gray-700 shadow-md">
              <div class="flex justify-between items-center mb-5 text-gray-500">
                  <span class="bg-primary-100 text-primary-800 text-xs font-sora inline-flex items-center py-0.5 rounded">
                    {{article.category}}
                  </span>
                  <span class="font-sora text-xs">{{article.createdAt}}</span>
              </div>
              <h2 class="mb-2 text-2xl font-sora text-md tracking-tight text-gray-50 dark:text-white"><a :href="`/wiki/${article.slug}`">{{article.title}}</a></h2>
              <p class="mb-5 font-sora text-gray-400">{{article.frase}}</p>
              <div class="flex justify-between items-center">
                  <div class="flex items-center space-x-4">
                      <img class="w-7 h-7 rounded-full" :src="article.avatar" :alt="article.author" />
                      <span class="font-sora text-white">
                          {{article.author}}
                      </span>
                  </div>
                  <a :href="`/wiki/${article.slug}`" class="inline-flex items-center font-sora text-blue-600">
                      Read more
                      <svg class="ml-2 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                  </a>
              </div>
          </article> 
      </div>  
  </div>
</section>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("wiki", params.slug)
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
    title: 'Wiki - Indonesia Project Zomboid',
    meta: [
      { 
        name: 'author', 
        content: 'Indonesia Project Zomboid' 
      },
      {
        name: 'description',
        content: 'Home for Project Zomboid mods from "Indonesia Project Zomboid" Community Server',
      },
      {
        key: 'og:title',
        property: 'og:title',
        content: 'Wiki - Indonesia Project Zomboid',
      },
      {
        key: 'og:description',
        property: 'og:description',
        content: 'Home for Project Zomboid mods from "Indonesia Project Zomboid" Community Server',
      },
      { 
        hid: 'og:image', 
        property: 'og:image', 
        content: 'https://www.projectzomboid.id/assets/img/hero-logo.png',
      },
      {
        key: 'og:url',
        property: 'og:url',
        content: 'https://mods.projectzomboid.id',
      },
      {
        key: 'twitter:title',
        name: 'twitter:title',
        content: 'Wiki - Indonesia Project Zomboid',
      },
      {
        key: 'twitter:card',
        name: 'twitter:card',
        content: 'summary',
      },
      {
        key: 'twitter:creator',
        name: 'twitter:creator',
        content: '@indonesiaprojectzomboid',
      },
      {
        key: 'twitter:description',
        name: 'twitter:description',
        content: 'Home for Project Zomboid mods from "Indonesia Project Zomboid" Community Server',
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