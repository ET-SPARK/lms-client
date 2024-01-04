            <!--  our vidio modal part that shows a vidio with some description  as a modal  -->


<template>
  <div
    class="bg-white fixed inset-0 flex items-center justify-center z-50 bg-black bg-opacity-50 overflow-y-auto"
    @click="closeModal"
  >
    <div
      class="w-full max-w-3xl p-4 bg-white rounded-lg shadow-lg"
      style="max-height: 90vh; overflow-y: auto"
      @click.stop
    >
      <!-- Video Section -->
      <div class="w-full mb-4">
        <video class="w-full" controls>
          <source src="../static/country-info.mp4" type="video/mp4" />
          Your browser does not support the video tag.
        </video>
      </div>

      <!-- Description and Language Sections -->
      <div class="w-full flex flex-wrap justify-between">
        <!-- Description Section -->
        <div class="w-full md:w-2/3 p-4">
          <h2 class="text-xl font-bold">{{ videoTitle }}</h2>
          <div class="mt-2 text-gray-600">{{ videoDescription }}</div>
          <div>
            <p class="mb-4">
              Are you struggling to communicate in English? We understand that
              it can be difficult to speak naturally in a new language, which is
              why we have developed an online course to help you master the art
              of conversation in English. Our course is designed for
            </p>
            <P class="mt-4">
              non-English speakers who want to expand their vocabulary and
              communicate effectively in everyday situations, whether it be
              making friends, conducting business, watching English films, or
              traveling to an English-speaking country. As the world's
            </P>
            <p class="mt-4">
              universal language, having a basic understanding of English is
              essential for functioning in most countries. However, our course
              will take your English skills to the next level, enabling you to
              communicate like a native and express even your most complex
              thoughts.
            </p>
          </div>
        </div>

        <!-- Language Section -->
        <div class="w-full md:w-1/3 p-4">
          <h3 class="text-lg font-bold m-2 text-center">
            ready to learn english
          </h3>

          <button
            class="mt-4 px-4 py-2 bg-blue text-white rounded-md w-full mb-4"
          >
            Buy Courses
          </button>
          <ul class="list-disc pl-4">
            <li class="flex items-center">Level : Intermediate</li>
            <li class="flex items-center mt-2">Language : አማርኛ</li>
            <li class="flex items-center mt-2">Subtitle : English, አማርኛ</li>
            <li class="flex items-center mt-2">Duration : 4፡00 h</li>
            <li class="flex items-center mt-2">Lessons : 28</li>
            <li class="flex items-center mt-2">Resources : 8</li>
            <li class="flex items-center mt-2">Quiz : 7</li>
            <li class="flex items-center mt-2">
              Access on mobile, desktop, and TV
            </li>
            <li class="flex items-center mt-2">
              Lifetime access to the community
            </li>
            <li class="flex items-center mt-2">Certificate of Completion</li>
          </ul>
        </div>
      </div>

      <button
        class="mt-4 px-4 py-2 bg-blue text-white rounded-md"
        @click="closeModal"
      >
        Close
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    videoUrl: {
      type: String,
      required: true,
    },
    videoTitle: {
      type: String,
      required: true,
    },
    videoDescription: {
      type: String,
      required: true,
    },
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
    preventClose(event) {
      event.stopPropagation();
    },
  },
};
</script>
