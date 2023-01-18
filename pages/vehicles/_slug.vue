<template>
  <div class="bg-slate-900">
    <article class="mx-[50vh] max-w-5xl tracking-wide px-6 xl:px-0 prose lg:prose-xl font-sora">
        <p class="font-sora text-sm font-bold text-white py-16"><NuxtLink to="/vehicles" class="text-white">← Back to Catalogue</NuxtLink></p>
      <div class="container py-2 mx-auto lg:flex lg:h-128">
        <div class="flex flex-col items-center w-full lg:flex-row lg:w-1/2">
            <div class="max-w-lg">
                <h1 class="text-xl tracking-wide text-white lg:text-3xl">{{ vehicles.title }}</h1>
                <div class="mt-6">
                    <div
                        class="inline-block px-4 py-2 font-semibold text-center text-white transition-colors duration-200 transform bg-blue-500 rounded-full hover:bg-blue-400">
                        {{vehicles.price}}</div>
                </div>
            </div>
        </div>
        <div class="flex items-center justify-center w-full mt-2 lg:h-96 lg:w-1/2">
            <img class="object-cover w-full max-w-2xl rounded-md lg:h-full"
            :src="vehicles.coverImage" :alt="vehicles.title">
        </div>
    </div>
    
<div class="relative overflow-x-auto">
    <p class="text-md tracking-wide text-white">General Specifications</p>
    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 rounded-lg">
        <tbody>
            <tr class="bg-gray-800 border-b border-gray-700 rounded-lg">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Type
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.type }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Horse Power
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.hp }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Seating
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.seating }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Tire
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.tire }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Spare Tire
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.spare_tire }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Gas Tank Capacity
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.gas_tank }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Snorkel
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.snorkel }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Bumper
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.bumper }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Roof Rails
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.roof_rails }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Roof Lights
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.roof_lights }}
                </td>
            </tr>
        </tbody>
    </table>
    <p class="text-md tracking-wide text-white">Storage Specifications</p>
    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 rounded-lg">
        <tbody>
            <tr class="bg-gray-800 border-b border-gray-700 rounded-lg">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Trunk
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.trunk }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Roof Rack
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.roof_rack }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Spare Wheel Rack
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.spare_wheel_rack }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Roof Tent
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.roof_tent }}
                </td>
            </tr>
        </tbody>
    </table>
    <p class="text-md tracking-wide text-white">Protection Specifications</p>
    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 rounded-lg">
        <tbody>
            <tr class="bg-gray-800 border-b border-gray-700 rounded-lg">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Bulbar
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.bulbar }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Windshield Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.windshield_armor }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Rear Windshield Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.rear_windshield_armor }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Front Left Door Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.front_l_door_armor }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Front Right Door Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.front_r_door_armor }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Rear Left Door Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.rear_l_door_armor }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Rear Right Door Armor
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.rear_r_door_armor }}
                </td>
            </tr>
        </tbody>
    </table>
    <p class="text-md tracking-wide text-white">Additional Info</p>
    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 rounded-lg">
        <tbody>
            <tr class="bg-gray-800 border-b border-gray-700 rounded-lg">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Fully Animated
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.fully_animated }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Can Tow or be Towed
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.tow_towed }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Can Change Colors
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.colorable }}
                </td>
            </tr>
            <tr class="bg-gray-800 border-b border-gray-700">
                <th scope="row" class="px-6 py-4 font-medium text-gray-400 whitespace-nowrap dark:text-white">
                    Can Change Skin
                </th>
                <td class="px-6 py-4">
                    {{ vehicles.skin }}
                </td>
            </tr>
        </tbody>
    </table>
    </div>
    <div class="h-10"></div>
    </article>
  </div>
  </template>
  
  <script>
  import YoutubeVideo from "../../components/global/YoutubeVideo.vue";
  export default {
    async asyncData({ $content, params }) {
      const vehicles = await $content("vehicles", params.slug).fetch();
      const [prev, next] = await $content("vehicles")
        .only(["title", "slug"])
        .sortBy("createdAt", "desc")
        .surround(params.slug)
        .fetch();
      return { vehicles, prev, next };
    },
  data() {
    return {
      vehicles: {},
    };
  },
  head() {
    return {
      title: this.vehicles.title ? `${this.vehicles.title}` : "",
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.vehicles.description,
        },
        { hid: "og-title", property: "og:title", content: this.vehicles.title },
        {
          hid: "og-image",
          property: "og:image",
          content: this.vehicles.coverImage,
        },
        { hid: "og-image-width", property: "og:image:width", content: 500 },
        { hid: "og-image-height", property: "og:image:height", content: 300 },
        {
          hid: "og-image-type",
          property: "og:image:type",
          content: "image/jpeg",
        },
      ],
      link: [{ rel: 'icon', type: 'image/x-icon', href: 'https://www.projectzomboid.id/assets/favicon.png' }],
    };
  },
    components: { YoutubeVideo },
  };
  </script>
  