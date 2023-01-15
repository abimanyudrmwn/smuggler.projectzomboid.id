<template>
<section class="bg-gray-900">
    <div class="py-8 px-4 mx-auto max-w-screen-xl text-center lg:py-16 lg:px-6">
        <div class="mx-auto mb-8 max-w-screen-sm lg:mb-16">
            <h2 class="mb-4 text-4xl tracking-tight font-sora text-white">Contributors</h2>
            <p class="font-sora text-gray-300 sm:text-xl">Cool peoples that help mods come to alive</p>
        </div> 
        <div class="grid gap-8 lg:gap-16 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3">
            <div v-for="contributors in current" :key="contributors.slug" class="text-center text-gray-500 dark:text-gray-400">
                <img class="mx-auto mb-4 w-36 h-36 rounded-full" :src="contributors.avatarsImage" alt="Bonnie Avatar">
                <h3 class="mb-1 text-2xl font-sora tracking-tight text-white">
                    <a>{{contributors.name}}</a>
                </h3>
                <p class="font-sora">{{contributors.contributor}}</p>
                <ul class="flex justify-center mt-4 space-x-4">
                    <li>
                        <a :href="contributors.url" target="_blank" class="text-[#39569c] hover:text-gray-50">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" class="bi bi-steam" viewBox="0 0 16 16">
                                <path d="M.329 10.333A8.01 8.01 0 0 0 7.99 16C12.414 16 16 12.418 16 8s-3.586-8-8.009-8A8.006 8.006 0 0 0 0 7.468l.003.006 4.304 1.769A2.198 2.198 0 0 1 5.62 8.88l1.96-2.844-.001-.04a3.046 3.046 0 0 1 3.042-3.043 3.046 3.046 0 0 1 3.042 3.043 3.047 3.047 0 0 1-3.111 3.044l-2.804 2a2.223 2.223 0 0 1-3.075 2.11 2.217 2.217 0 0 1-1.312-1.568L.33 10.333Z"/>
                                <path d="M4.868 12.683a1.715 1.715 0 0 0 1.318-3.165 1.705 1.705 0 0 0-1.263-.02l1.023.424a1.261 1.261 0 1 1-.97 2.33l-.99-.41a1.7 1.7 0 0 0 .882.84Zm3.726-6.687a2.03 2.03 0 0 0 2.027 2.029 2.03 2.03 0 0 0 2.027-2.029 2.03 2.03 0 0 0-2.027-2.027 2.03 2.03 0 0 0-2.027 2.027Zm2.03-1.527a1.524 1.524 0 1 1-.002 3.048 1.524 1.524 0 0 1 .002-3.048Z"/>
                            </svg>
                        </a>
                    </li>
                </ul>
            </div>
        </div>  
    </div>
</section>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const contributors = await $content("contributor", params.slug)
      .fetch();

    const all = contributors.map((e) => e.category);
    const categories = [...new Set(all)];

    const title = "Newest Article";
    const current = contributors;
    return {
      contributors,
      categories,
      title,
      current,
    };
  },
    head: {
    title: 'Contributors - Indonesia Project Zomboid',
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
        content: 'Contributors - Indonesia Project Zomboid',
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
        content: 'Contributors - Indonesia Project Zomboid',
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