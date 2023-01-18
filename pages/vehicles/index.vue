<template>
    <div class="bg-gray-900 py-10">
    <div class="mx-auto max-w-5xl tracking-wide px-4 xl:px-0">
        <h1 class="font-sora text-2xl text-white">Vehicles Catalogue</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 py-10">
      <div v-for="vehicles in current" :key="vehicles.slug" class="border border-gray-700 rounded-xl shadow-lg">
            <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
              <a :href="`/vehicles/${vehicles.slug}`">
                <img alt="vehicles Image" class="lazyLoad isLoaded object-fill h-96 w-120" :src="vehicles.coverImage">
              </a>
            </div>
            <div class="p-3 pr-2"><div class="h-2"></div> 
            <h2 class="font-sora text-2xl font-bold text-white">
              <a :href="`/vehicles/${vehicles.slug}`">
                {{ vehicles.title }}
              </a>
            </h2> 
                <div class="h-1"></div>
                <p class="font-sora text-md font-light text-gray-200 leading-5">Specifications :</p>
                <ul class="flex justify-between text-white pr-2">
                    <li class="underline">
                        Type
                    </li>
                    <li class="font-bold">
                        {{ vehicles.type }}
                    </li>
                </ul>
                <ul class="flex justify-between text-white pr-2">
                    <li class="underline">
                        HP
                    </li>
                    <li class="font-bold">
                        {{ vehicles.hp }}
                    </li>
                </ul>
                <ul class="flex justify-between text-white pr-2">
                    <li class="underline">
                        Seating
                    </li>
                    <li class="font-bold">
                        {{ vehicles.seating }}
                    </li>
                </ul>
            <div class="h-6">
            </div> 
            <div class="flex justify-between items-end">
              <span class="bg-green-600 text-white px-4 py-2 rounded-full text-md font-bold">{{ vehicles.price }}</span> 
              <a class="hover:bg-gray-100 hover:text-gray-900 text-white px-4 py-2 rounded-full font-bold" :href="`/vehicles/${vehicles.slug}`">🔐 Top Secret →&#xFEFF;</a>
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
      const vehicles = await $content("vehicles", params.slug)
        .sortBy("price", "asc")
        .fetch();
  
      const all = vehicles.map((e) => e.category);
      const categories = [...new Set(all)];
  
      const title = "vehicles";
      const current = vehicles;
      return {
        vehicles,
        categories,
        title,
        current,
      };
    },
    head: {
    title: 'vehicles - Indonesia Project Zomboid',
    meta: [
      { 
        name: 'author', 
        content: 'Indonesia Project Zomboid' 
      },
      {
        name: 'description',
        content: 'Home for Project Zomboid vehicles from "Indonesia Project Zomboid" Community Server',
      },
      {
        key: 'og:title',
        property: 'og:title',
        content: 'vehicles - Indonesia Project Zomboid',
      },
      {
        key: 'og:description',
        property: 'og:description',
        content: 'Home for Project Zomboid vehicles from "Indonesia Project Zomboid" Community Server',
      },
      { 
        hid: 'og:image', 
        property: 'og:image', 
        content: 'https://www.projectzomboid.id/assets/img/hero-logo.png',
      },
      {
        key: 'og:url',
        property: 'og:url',
        content: 'https://vehicles.projectzomboid.id',
      },
      {
        key: 'twitter:title',
        name: 'twitter:title',
        content: 'vehicles - Indonesia Project Zomboid',
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
        content: 'Home for Project Zomboid vehicles from "Indonesia Project Zomboid" Community Server',
      }
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: 'https://www.projectzomboid.id/assets/favicon.png' }],
  },
    methods: {
      reset() {
        this.title = "vehicles";
        this.current = this.vehicles;
      },
      filter(value) {
        this.title = value;
        this.current = this.vehicles.filter((e) => e.category == value);
      },
    },
  };
  </script>