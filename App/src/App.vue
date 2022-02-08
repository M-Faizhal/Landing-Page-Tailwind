<script setup>
  import BriefcaseIcon from "./icon/briefcase.svg";
  import LocationIcon from "./icon/location.svg";
  import ProfileIcon from "./icon/profile.svg";

  const menu = ["Home", "About Us", "Blogs", "Contact"];
  const features = [
      {
        icon: BriefcaseIcon,
        title: "Work-Life Balance",
        description:
          "Many remote jobs also come with flexible schedules, which means that workers can start and end their day as they choose.",
        color: "bg-orange",
      },
      {
        icon: LocationIcon,
        title: "Work Anywhere",
        description:
          "Having access to a broader range of job opportunities that aren’t limited by geographic location. This can be especially helpful.",
        color: "bg-blue",
      },
      {
        icon: ProfileIcon,
        title: "Improved Inclusivity",
        description:
          "Remote work enables companies to embrace diversity and inclusion by hiring people from different backgrounds.",
        color: "bg-pink",
      },
  ];
</script>
<template>
  <div class="w-full min-h-screen font-sans text-gray-900">
    <div class="bg-gradient-to-b from-[#FEE6F7] to-white">
      <img src="/img/blob.svg" alt="" class="absolute top-0 right-0 pointer-events-none">
      <div class="px-6 mx-auto max-w-6xl">
        <div class="flex justify-between items-center py-10">
          <img src="./icon/logo.svg" alt="">
          <nav class="hidden md:flex md:items-center md:space-x-10">
            <a v-for="item in menu" :key="item.id" href="#" class="text-gray-700 hover:text-gray-900">{{ item }}</a>
            <a href="#" class="font-semibold text-indigo-600 hover:text-indigo-800">Try now</a>
          </nav>
          <button class="p-4 md:hidden">
            <img src="./icon/menu.svg" alt="" class="w-6 h-6 text-gray-800">
          </button>
        </div>
      </div>
    </div>
    <div class="px-6 mx-auto max-w-6xl">
      <div class="flex flex-col-reverse items-center md:flex-row lg:items-end">
        <div class="pt-24 md:w-1/2 pb-24 text-center md:pb-12 pr-8 md:text-left">
          <h2 class="text-5xl md:text-6xl font-bold font-display z-10">Learn the <span class="relative after:content-[url(/img/scratch.svg)] after:absolute after:-top-2 after:-right-6 after:-z-1">best</span> ways for staying <span class="relative after:content-[url(/img/decoration.svg)] after:absolute after:-bottom-2 after:-right-8 after:-z-1">productive</span></h2>
          <p class="pt-8 md:max-w-md text-lg leading-relaxed text-gray-500 md:text-xl">Working at home is definitely a convenient option and makes sense in these unprecedented times.</p>
          <nav class="flex justify-center items-center pt-12 space-x-6 md:justify-start">
            <button class="flex justify-center items-center py-4 px-8 font-bold tracking-wide leading-7 text-white bg-blue-600 rounded-xl hover:shadow-xl">Get Tips</button>
            <button class="flex items-center">
              <img src="./icon/play-button.svg" class="drop-shadow-lg hover:drop-shadow-xl" alt="">
              <span class="pl-4 font-bold tracking-wide">Learn More</span>
            </button>
          </nav>
        </div>
        <div class="w-1/2 flex items-end border-b border-gray-400">
          <img src="/img/illustration.svg" alt="">
        </div>
      </div>
    </div>
    <div class="bg-gray-50">
      <div class="py-12 px-6 mx-auto max-w-6xl">
        <div class="flex flex-col md:flex-row gap-5">
          <div v-for="feature in features" :key="feature.id" class="flex flex-col p-8 space-y-4 bg-white rounded-lg border border-gray-200 transition-shadow duration-500 ease-out hover:shadow-xl cursor-pointer">
            <div class="flex items-center space-x-3">
              <div class="relative">
                <span :class="feature.color" class="absolute top-0 left-4 w-3 h-3 rounded-full opacity-50"></span>
                <Component :is="feature.icon" class="relative" />
              </div>
              <div class="relative">
                <span :class="feature.color" class="absolute right-0 bottom-1 w-12 h-1.5 opacity-60" />
                <h2 class="relative text-xl font-display"> {{feature.title}} </h2>
              </div>
            </div>
            <p class="text-sm leading-relaxed text-gray-500">{{feature.description}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>