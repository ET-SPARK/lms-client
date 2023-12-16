<template>
  <Header />
  <div class="flex justify-between ml-20 mr-20 mt-10">
    <section>1</section>
    <section class="flex1 bg-gray-200 w-[350px]">
      <div class="text-center border-b-2 border-gray-100 p-4">
        <p class="mt-2">Ready to become web developer?</p>
        <button
          class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 mt-2 w-[320px] rounded-l"
        >
          Register Now
        </button>
      </div>
      <div class="flex1 ml-4">
        <div class="p-2">
          <Icon
            name="carbon:skill-level-basic"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Level : Beginner
        </div>
        <div class="p-2">
          <Icon
            name="lucide:languages"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Language : አማርኛ
        </div>
        <div class="p-2">
          <Icon
            name="tdesign:subtitle"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Subtitle : አማርኛ, English
        </div>
        <div class="p-2">
          <Icon
            name="material-symbols:alarm-on-outline"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Duration : 4:00 h
        </div>
        <div class="p-2">
          <Icon
            name="material-symbols-light:play-lesson-outline"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Lessons : 58
        </div>

        <div class="p-2">
          <Icon
            name="material-symbols:library-books-outline"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Resources : 12
        </div>
        <div class="p-2">
          <Icon
            name="material-symbols:quiz-outline"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Quiz : 8
        </div>
        <div class="p-2">
          <Icon
            name="ic:outline-tv"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Access on mobile, desktop, and TV
        </div>
        <div class="p-2">
          <Icon
            name="streamline:interface-page-controller-button-loop-1-multimedia-multi-button-repeat-media-loop-infinity-controls"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Lifetime access to the community
        </div>
        <div class="p-2">
          <Icon
            name="teenyicons:certificate-outline"
            class="cursor-pointer mr-1"
            color="#212F3D"
          />Certificate of Completion
        </div>
      </div>
    </section>
  </div>
  <About />
  <Footer />
</template>
