<template>
    <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
      <nav class="rounded-md w-full mt-6 mb-4">
        <ol class="list-reset flex">
          <li><a class="font-sora text-blue-600 hover:text-blue-700"><router-link to="/">Home</router-link></a></li>
          <li><span class="text-gray-500 mx-2 font-sora">/</span></li>
          <li class="text-gray-500 font-sora">Portfolio</li>
        </ol>
      </nav>
    <h2 class="text-2xl font-bold font-sora mb-10">{{title}}</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
      <div v-for="portfolio in current" :key="portfolio.slug" class="border border-gray-100 rounded-xl shadow-lg">
            <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
              <router-link :to="`/portfolio/${portfolio.slug}`">
                <img alt="portfolio Image" class="lazyLoad isLoaded object-scale-down" :src="`/images/covers/${portfolio.coverImage}`">
              </router-link>
            </div>
            <div class="p-3 pr-2"><div class="h-2"></div> 
            <h2 class="font-sora text-md font-bold">
              <router-link :to="`/portfolio/${portfolio.slug}`">
                {{ portfolio.title }}
              </router-link>
            </h2> 
            <div class="h-2"></div> 
              <p class="font-sora text-md font-light text-gray-600 leading-5">
                {{ portfolio.frase }}
                </p> 
            <div class="h-6">
            </div> 
            <div class="flex justify-between items-end">
              <span class="bg-green-50 text-green-600 px-4 py-2 rounded-full text-sm font-sora">{{ portfolio.category }}</span> 
              <a class="hover:bg-gray-100 px-4 py-2 rounded-full text-md"><router-link :to="`/portfolio/${portfolio.slug}`">Project Details →&#xFEFF;</router-link></a>
            </div>
          </div>
        </div>
    </div>
  
    <footer class="py-10 px-5 text-center mx-auto max-w-5xl">
        <span class="font-sora font-md text-md">
              <a href="https://github.com/abimanyudrmwn" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Github</span></a>,
              <a href="https://youtube.com/@abimanyudrmwn" title="abimanyudrmwn - Youtube" target="_blank" class="underline text-gray-700"><span>Youtube</span></a>,
              <a href="https://instagram.com/drmwnspace" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Instagram</span></a>
            </span>
          <p class="mt-6 text-sm text-gray-500">©2022 DrmwnSpace - Build with Vue + Nuxt ❤️ Tailwind CSS</p>
      </footer>
  
  </div>
  </template>
  
  <script>
  export default {
    async asyncData({ $content, params }) {
      const portfolio = await $content("portfolio", params.slug)
        .sortBy("createdAt", "asc")
        .limit(2)
        .fetch();
  
      const all = portfolio.map((e) => e.category);
      const categories = [...new Set(all)];
  
      const title = "Portfolio";
      const current = portfolio;
      return {
        portfolio,
        categories,
        title,
        current,
      };
    },
    methods: {
      reset() {
        this.title = "Portfolio";
        this.current = this.portfolio;
      },
      filter(value) {
        this.title = value;
        this.current = this.portfolio.filter((e) => e.category == value);
      },
    },
  };
  </script>