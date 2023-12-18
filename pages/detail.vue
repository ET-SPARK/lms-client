<template>
  <Header />
  <div class="flex justify-between ml-20 mr-20 mt-10">
    <section class="flex1">
      <div>
        <p class="text-4xl font-bold">
          Learn English: Upgrade Your Speaking and Listening Skill
        </p>
      </div>
      <div class="flex items-center">
        <div class="mt-4">
          <img src="/images/profile.jpg" class="w-20 h-20 rounded-full" />
        </div>
        <NuxtLink to="#"
          ><div class="ml-5 text-gray-500 hover:text-blue-500">
            A course by <br />
            Abebe
          </div></NuxtLink
        >
      </div>
      <div class="mb-6 rounded-xl">
        <iframe
          width="750"
          height="450"
          src="https://www.youtube.com/embed/yYF2Vf1Gc14?si=o4MaabEp_FWPTcMn"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          allowfullscreen
        ></iframe>
      </div>
      <div class="flex1 bg-gray-200 w-[750px] rounded-l">
        <div class="flex justify-between items-center p-4">
          <div>
            <p class="text-2xl font-bold">About the Course</p>
          </div>
          <div
            class="border border-blue-500 hover:border-blue-600 hover:bg-blue-100 p-2 rounded-xl"
          >
            <Icon name="ic:twotone-share" class="text-blue-600 text-xl" />
            <button class="pl-2 text-lg text-blue-600">share</button>
          </div>
        </div>
        <div class="p-4 text-justify">
          <p class="mt-2">
            Are you struggling to communicate in English? We understand that it
            can be difficult to speak naturally in a new language, which is why
            we have developed an online course to help you master the art of
            conversation in English. Our course is designed for non-English
            speakers who want to expand their vocabulary and communicate
            effectively in everyday situations, whether it be making friends,
            conducting business, watching English films, or traveling to an
            English-speaking country.
          </p>
          <p class="mt-2">
            As the world's universal language, having a basic understanding of
            English is essential for functioning in most countries. However, our
            course will take your English skills to the next level, enabling you
            to communicate like a native and express even your most complex
            thoughts. Our comprehensive curriculum covers all aspects of the
            English language, including grammar, vocabulary, and pronunciation,
            with a focus on real-life scenarios.
          </p>
          <p class="mt-2">
            Upon completion of our course, you'll be able to navigate through
            any English-speaking country with ease, connect with locals and
            other travelers, conduct business, enroll in classes, and so much
            more. We strive to make our course accessible and easy to understand
            for non-English speakers, so whether you're a beginner or an
            intermediate speaker, our course will help you achieve your goals.
          </p>
          <p class="mt-2 text-2xl font-bold">Requirements</p>
          <ul class="mt-2 list-disc ml-10">
            <li>Basic understanding of computers and the internet</li>
            <li>
              Familiarity with social media platforms (helpful, but not
              required)
            </li>
            <li>
              Access to a computer or mobile device with a stable internet
              connection
            </li>
          </ul>
          <p class="mt-2 text-2xl font-bold">Who is this course for?</p>
          <ul class="mt-2 list-disc ml-10">
            <li>
              Non-native English speakers who want to improve their fluency and
              pronunciation
            </li>
            <li>
              English language learners who want to improve their listening
              comprehension
            </li>
            <li>
              Business professionals who want to improve their English
              communication skills
            </li>
            <li>
              Students who need to pass an English proficiency test for academic
              or professional purposes
            </li>
            <li>
              Anyone who wants to gain confidence speaking and listening in
              English.
            </li>
          </ul>
        </div>
        <div class="p-4">
          <p class="font-bold text-2xl">What you will learn</p>
          <div class="m-5">
            <div class="p-4 mt-4 bg-gray-100" @click="toggleLesson">
              <button class="text-xl">
                <div class="flex justify-between w-[650px]">
                  <div>
                    <span class="font-bold">Contents</span>
                  </div>
                  <div>
                    <Icon
                      name="material-symbols:arrow-drop-down"
                      class="cursor-pointer"
                      color="black"
                    />
                  </div>
                </div>
              </button>
              <div v-if="showLesson" class="p-4">
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">Lesson 1 : Why Learn English?</div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 2 : English Language Basics Part 1
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 3 : English Language Basics Part 2
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 4 : How to make business phone calls in English
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 5 : How to introduce yourself and others in English
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 6 : How to make small talk in English
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 7 : How to ask for and give directions in English
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 8 : How to order food in English
                  </div>
                </div>
                <div class="p-1 flex items-center">
                  <div>
                    <Icon
                      name="material-symbols:play-arrow-outline"
                      class="cursor-pointer text-xl"
                      color="black"
                    />
                  </div>
                  <div class="ml-2">
                    Lesson 9 : How to talk about hobbies and interests in
                    English
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="flex1 bg-gray-200 w-[350px] rounded-l h-[530px]">
      <div class="text-center border-b-2 border-gray-100 p-4">
        <p class="mt-2">Ready to learn English?</p>
        <button
          class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 mt-2 w-[320px] rounded-l"
        >
          Register Now
        </button>
      </div>
      <div class="flex1 ml-4 mb-4">
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

<script>
export default {
  data() {
    return {
      showLesson: false,
    };
  },
  methods: {
    toggleLesson() {
      // Toggle the value of showLesson when the button is pressed
      this.showLesson = !this.showLesson;
    },
  },
};
</script>
