<template>
  <section>
    <div class="mx-auto max-w-5xl tracking-wide px-6 xl:px-0">
      <div class="h-24"></div>
        <div class="text-center">
          <h1 class="font-sora text-4xl leading-tight md:text-6xl md:leading-tight lg:text-6xl lg:leading-tight xl:text-5xl font-semibold xl:leading-tight">
            I'm Abimanyu Darmawan - Frontend Developer, Graphic Designer and Game Development Enthusiast
          </h1>
          <div class="h-8"></div>
          <span class="font-sora font-md text-lg">
            <a href="https://github.com/abimanyudrmwn" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Github</span></a>,
            <a href="https://youtube.com/@abimanyudrmwn" title="abimanyudrmwn - Youtube" target="_blank" class="underline text-gray-700"><span>Youtube</span></a>,
            <a href="https://instagram.com/drmwnspace" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Instagram</span></a>
          </span>
          <div class="h-16"></div>
        </div>
    </div>

    <div class="mx-auto max-w-6xl tracking-wide px-6 xl:px-0">
      <div class="h-24"></div>
      <div class="flex flex-col items-center">
        <h2 class="text-2xl font-light font-sora">Featured Works</h2>
        <div class="h-2 w-20 bg-gray-100 rounded-full mt-3"></div>
      </div>
      <div class="h-28"></div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
      </div>
    </div>

    <div class="h-40"></div>

    <div class="py-14">
      <div class="text-center">
        <div class="flex flex-col items-center">
          <h2 class="text-2xl font-light font-sora">Let's work together</h2> 
          <div class="h-2 w-20 bg-gray-100 rounded-full mt-3"></div></div> 
        <div class="h-20"></div> 
        <a href="mailto:hi@drmwn.space" title="contact" class="text-3xl font-sora text-gray-600">hi@drmwn.space</a>
      </div>
    </div>

    <div class="h-32"></div>

    <footer class="py-10 px-5 text-center mx-auto max-w-5xl">
      <span class="font-sora font-md text-md">
            <a href="https://github.com/abimanyudrmwn" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Github</span></a>,
            <a href="https://youtube.com/@abimanyudrmwn" title="abimanyudrmwn - Youtube" target="_blank" class="underline text-gray-700"><span>Youtube</span></a>,
            <a href="https://instagram.com/drmwnspace" title="abimanyudrmwn - Github" target="_blank" class="underline text-gray-700"><span>Instagram</span></a>
          </span>
        <p class="font-sora mt-6 text-sm text-gray-500">©2022 DrmwnSpace - Build with Vue + Nuxt ❤️ Tailwind CSS</p>
    </footer>

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
