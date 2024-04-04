<template>
  <div class="w-full flex flex-col-reverse p-4 md:flex-row md:p-8 lg:p-16">
    <img
      alt="image"
      src="../../static/images/studentImg.webp"
      class="home-image w-full h-auto object-cover self-center rounded-full border-8 border-b-background border-t-background mr-10 max-[640px]:mt-10 max-[640px]:mr-0 md:w-1/4 max-[640px]:w-2/3 lg:w-1/3 rotate-circle"
    />
    <div
      class="w-full flex flex-col mt-4 items-center md:justify-center md:items-start max-w-4xl mx-auto"
    >
      <div class="mb-2 text-2xl text-center font-semibold max-[640px]:text-sm">
        <span class="typing-animation">
          Unlock Your Potential with Lifelong Learning</span
        >
      </div>
      <div class="text-lg font-light mb-2 md:text-xl">
        Join Our Community Today!
      </div>
      <div
        class="flex-shrink-0 w-full mt-6 h-auto flex items-start flex-row justify-center md:justify-start"
      >
        <NuxtLink to="/home">
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

<style>
@keyframes rotateCircle {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.rotate-circle {
  animation: rotateCircle 60s linear infinite; /* Adjust the duration and timing function as needed */
}

.typing-animation {
  overflow: hidden;
  padding: 8px;
  white-space: nowrap;
  border-right: 2px solid; /* Adjust border as needed */
  display: inline-block;
  animation: typing 15s steps(40, end) infinite; /* Adjust duration and steps as needed */
}

@keyframes typing {
  0% {
    width: 0;
  }
  50% {
    width: 100%;
  }
  100% {
    width: 100%;
  }
}
</style>
