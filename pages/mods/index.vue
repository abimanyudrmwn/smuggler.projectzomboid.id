<template>
    <div class="bg-gray-900 py-10">
    <div class="mx-auto max-w-5xl tracking-wide px-4 xl:px-0">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 py-10">
      <div v-for="mods in current" :key="mods.slug" class="border border-gray-700 rounded-xl shadow-lg">
            <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
              <a target="_blank" :href="mods.url">
                <img alt="mods Image" class="lazyLoad isLoaded object-scale-down" :src="mods.coverImage">
              </a>
            </div>
            <div class="p-3 pr-2"><div class="h-2"></div> 
            <h2 class="font-sora text-md font-bold text-white">
              <a target="_blank" :href="mods.url">
                {{ mods.title }}
              </a>
            </h2> 
            <div class="h-2"></div> 
              <p class="font-sora text-md font-light text-gray-200 leading-5">
                {{ mods.description }}
                </p> 
            <div class="h-6">
            </div> 
            <div class="flex justify-between items-end">
              <span class="bg-green-50 text-green-800 px-4 py-2 rounded-full text-sm font-medium">{{ mods.category }}</span> 
              <a class="hover:bg-gray-100 hover:text-gray-900 text-white px-4 py-2 rounded-full font-medium" :href="mods.url" target="_blank">Steam Workshops →&#xFEFF;</a>
            </div>
          </div>
        </div>
        </div>  
        <div class="h-16"></div>
      </div>
  </div>
  </template>
  
  <script>
  export default {
    async asyncData({ $content, params }) {
      const mods = await $content("mods", params.slug)
        .sortBy("createdAt", "asc")
        .limit(2)
        .fetch();
  
      const all = mods.map((e) => e.category);
      const categories = [...new Set(all)];
  
      const title = "Mods";
      const current = mods;
      return {
        mods,
        categories,
        title,
        current,
      };
    },
    head: {
    title: 'Mods - Indonesia Project Zomboid',
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
        content: 'Mods - Indonesia Project Zomboid',
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
        content: 'Mods - Indonesia Project Zomboid',
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
      reset() {
        this.title = "Mods";
        this.current = this.mods;
      },
      filter(value) {
        this.title = value;
        this.current = this.mods.filter((e) => e.category == value);
      },
    },
  };
  </script>