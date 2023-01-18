<template>
  <section class="bg-gray-900 py-24">
    <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
      <div class="h-3"></div>
        <div class="text-center">
          <h1 class="text-white font-sora text-4xl leading-tight md:text-4xl md:leading-tight lg:text-4xl lg:leading-tight xl:text-4xl font-semibold xl:leading-tight">
            Welcome to Smuggler
          </h1>
          <p class="font-sora text-sm text-white">Ssshh, don't tell anyone that im here.</p>
          <div class="h-16"></div>
        </div>
        <div class="h-6"></div>
        <div class="grid grid-cols-2 gap-10 py-10">
          <div class="border border-gray-700 rounded-xl shadow-lg">
              <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
                  <router-link to="/vehicles">
                  <img alt="mods Image" class="lazyLoad isLoaded object-scale-down" src="https://res.cloudinary.com/belanga/image/upload/v1674048364/ipz/cover-01_pgvfnv.jpg">
                  </router-link>
              </div>
              <div class="p-3 pr-2 items-center"><div class="h-2"></div> 
              <h2 class="font-sora text-4xl font-bold text-white text-center">
                <router-link to="/vehicles">
                  Vehicles & Trailers
                </router-link>
              </h2> 
              <div class="h-2"></div> 
                  <p class="mx-10 font-sora text-sm font-light text-gray-400 leading-2 text-center prose-sm">
                    Get ready for an adventure of a lifetime with our top-of-the-line vehicles! These babies will take you on a wild ride and make every moment unforgettable! So, why wait? Grab the keys and let's hit the road!
                  </p> 
              <div class="h-6">
              </div> 
              <div class="flex items-center justify-center py-3">
                <router-link to="/vehicles">
                <button class="bg-gray-800 hover:bg-gray-600 animate-pulse px-32 mx-auto my-auto rounded-full text-white text-2xl font-sora">Explore</button>
                </router-link>
              </div>
              </div>
          </div>
          <div class="border border-gray-700 rounded-xl shadow-lg">
            <div class="overflow-hidden rounded-xl" style="background-color:#f9f1f9">
                <router-link to="/weapons">
                <img alt="mods Image" class="lazyLoad isLoaded object-scale-down" src="https://res.cloudinary.com/belanga/image/upload/v1674048364/ipz/cover-02_skadzd.jpg">
                </router-link>
            </div>
            <div class="p-3 pr-2 items-center"><div class="h-2"></div> 
            <h2 class="font-sora text-4xl font-bold text-white text-center">
              <router-link to="/weapons">
                Weapons & Antique
              </router-link>
            </h2> 
            <div class="h-2"></div> 
            <p class="mx-10 font-sora text-sm font-light text-gray-400 leading-2 text-center prose-sm">
              Are you tired of being a victim to those brain-eating zombies? It's time to take back control and show them who's the real boss. And what better way to do that than with our top-of-the-line, beastly weapons.
                </p> 
            <div class="h-6">
            </div> 
            <div class="flex items-center justify-center py-3">
              <router-link to="/weapons">
              <button class="bg-gray-800 hover:bg-gray-600 animate-pulse px-32 mx-auto my-auto rounded-full text-white text-2xl font-sora">Explore</button>
              </router-link>
            </div>
            </div>
        </div>
        </div>  
        <div class="h-16"></div>
    </div>
  </section>
</template>

<script>

export default {
  head: {
    title: 'Smuggler - Indonesia Project Zomboid',
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
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: 'https://www.projectzomboid.id/assets/favicon.png' }],
    },
  }

</script>
