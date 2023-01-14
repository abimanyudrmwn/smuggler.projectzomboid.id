<template>
    <div class="bg-gray-900">
      <div class="mx-auto max-w-5xl tracking-wide px-4 xl:px-0">
    <h2 class="text-2xl font-bold font-sora mb-10 py-10 text-white">{{title}}</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
      <div v-for="mods in current" :key="mods.slug" class="border border-gray-700 rounded-xl shadow-lg">
            <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
              <router-link :to="`/mods/${mods.slug}`">
                <img alt="mods Image" class="lazyLoad isLoaded object-scale-down" :src="`/images/covers/${mods.coverImage}`">
              </router-link>
            </div>
            <div class="p-3 pr-2"><div class="h-2"></div> 
            <h2 class="font-sora text-md font-bold text-white">
              <router-link :to="`/mods/${mods.slug}`">
                {{ mods.title }}
              </router-link>
            </h2> 
            <div class="h-2"></div> 
              <p class="font-sora text-md font-light text-gray-200 leading-5">
                {{ mods.frase }}
                </p> 
            <div class="h-6">
            </div> 
            <div class="flex justify-between items-end">
              <span class="bg-green-50 text-green-800 px-4 py-2 rounded-full text-sm font-medium">{{ mods.category }}</span> 
              <a class="hover:bg-gray-100 hover:text-gray-900 text-white px-4 py-2 rounded-full font-medium" :href="mods.url" target="_blank">Project Details →&#xFEFF;</a>
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