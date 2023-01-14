<template>
  <section class="bg-gray-900">
    <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
      <div class="h-24"></div>
        <div class="text-center">
          <h1 class="text-white font-sora text-3xl leading-tight md:text-3xl md:leading-tight lg:text-3xl lg:leading-tight xl:text-3xl font-semibold xl:leading-tight">
            Home for Project Zomboid mods from "Indonesia Project Zomboid" Community Server
          </h1>
          <div class="h-16"></div>
        </div>
        <div class="flex flex-col items-center">
          <h2 class="text-2xl font-light font-sora text-gray-300">Featured Mods</h2>
        <div class="h-2 w-20 bg-gray-100 rounded-full mt-3"></div>
        </div>
        <div class="h-8"></div>
        <FeaturedMods />
        <div class="h-16"></div>
    </div>
  </section>
</template>

<script>

export default {
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
  }

</script>
