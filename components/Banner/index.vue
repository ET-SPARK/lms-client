<template>
  <div class="w-full flex flex-col-reverse p-4 md:flex-row md:p-8 lg:p-16">
    <img
      alt="image"
      src="../../static/images/studentImg.webp"
      class="home-image w-full h-auto object-cover self-center rounded-full border-8 border-b-background border-t-background mr-10 max-[640px]:mt-10 max-[640px]:mr-0 md:w-1/2 lg:w-1/3"
    />
    <div
      class="w-full flex flex-col mt-4 items-center md:justify-center md:items-start max-w-4xl mx-auto"
    >
      <h1 class="mb-2 text-xl text-center font-semibold md:text-xl lg:text-2xl">
        Unlock Your Potential with Lifelong Learning
      </h1>
      <h2 class="text-lg font-light mb-2 md:text-xl">
        Join Our Community Today!
      </h2>
      <div
        class="flex-shrink-0 w-full mt-6 h-auto flex items-start flex-row justify-center md:justify-start"
      >
        <NuxtLink to="/login">
          <Button
            class="px-4 py-2 text-sm transition duration-300 ml-4 md:px-6 md:py-4 md:text-md lg:px-8 lg:py-6 lg:text-lg"
          >
            Learner
          </Button>
        </NuxtLink>
        <Button
          class="px-4 py-2 text-sm transition duration-300 ml-4 md:px-6 md:py-4 md:text-md lg:px-8 lg:py-6 lg:text-lg"
        >
          Teacher
        </Button>
      </div>
    </div>
  </div>
</template>
import type { NuxtLink } from '#build/components';
