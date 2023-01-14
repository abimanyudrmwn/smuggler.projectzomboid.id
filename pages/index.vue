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
    title: 'DrmwnSpace - Homepage',
    meta: [
      { 
        name: 'author', 
        content: 'Abimanyu Darmawan' 
      },
      {
        name: 'description',
        content: 'Hello I&#39;am Abimanyu - Frontend Developer, Graphic Designer and Game Development Enthusiast',
      },
      {
        key: 'og:title',
        property: 'og:title',
        content: 'DrmwnSpace - Homepage',
      },
      {
        key: 'og:description',
        property: 'og:description',
        content: 'Hello Iam Abimanyu - Frontend Developer, Graphic Designer and Game Development Enthusiast',
      },
      { 
        hid: 'og:image', 
        property: 'og:image', 
        content: 'https://res.cloudinary.com/belanga/image/upload/v1650919422/drmwnicon-01_spqbmw.jpg',
      },
      {
        key: 'og:url',
        property: 'og:url',
        content: 'https://drmwn.space',
      },
      {
        key: 'twitter:title',
        name: 'twitter:title',
        content: 'DrmwnSpace - Homepage',
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
        content: 'Hello I&#39;am Abimanyu - Frontend Developer, Graphic Designer and Game Development Enthusiast',
      }
    ]
  },
  }

</script>
