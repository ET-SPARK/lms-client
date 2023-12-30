<template>
  <AuthHeader />
  <div class="mt-4 p-8">
    <section class="flex1 w-full">
      <!-- cource title -->
      <div>
        <p class="text-4xl font-bold max-[600px]:text-xl">
          Learn English: Upgrade Your Speaking and Listening Skill
        </p>
      </div>

      <!-- profile -->
      <div class="flex items-center">
        <div class="mt-4">
          <img
            src="https://iuenrktegcxhmvoeyhjh.supabase.co/storage/v1/object/public/instructor/avatar/nabil-emil.jpg?v=5"
            class="w-full h-20 rounded-full"
          />
        </div>
        <NuxtLink to="#"
          ><div class="ml-5 text-gray-500 hover:text-blue-500">
            A course by <br />
            Abebe
          </div></NuxtLink
        >
      </div>

      <div>
        <div>
          <!-- video player -->
          <iframe
            :src="`${selectedValue}?autoplay=1`"
            width="700"
            height="400"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe>
        </div>
        <div>
          <!-- course play list -->
          <div class="p-4 bg-gray-200 h-fit">
            <div class="mb-4">
              <span class="font-bold text-2xl">Contents</span>
            </div>
            <div class="bg-white p-4">
              <Accordion
                type="single"
                class="w-full text-start items-start max-[640px]:text-sm"
                collapsible
                :default-value="defaultValue"
              >
                <AccordionItem
                  v-for="item in accordionItems"
                  :key="item.value"
                  :value="item.value"
                >
                  <AccordionTrigger class="hover:no-underline">{{
                    item.title
                  }}</AccordionTrigger>
                  <AccordionContent>
                    <!-- Add a nested loop to iterate over content items -->
                    <ul>
                      <li
                        v-for="(contentItem, index) in item.content"
                        :key="index"
                        class="p-2"
                      >
                        <div
                          class="cursor-pointer"
                          @click="handleItemClick(contentItem.value)"
                        >
                          {{ contentItem.label }}
                        </div>
                      </li>
                    </ul>
                  </AccordionContent>
                </AccordionItem>
              </Accordion>
            </div>
          </div>
          <!-- course detail  -->
          <div class="flex1 bg-gray-200 mt-2">
            <!-- course detail -->
            <div>
              <div class="p-4">
                <div>
                  <p class="text-2xl font-bold">About the Course</p>
                </div>
              </div>
              <div class="p-4 text-justify">
                <p class="mt-2">
                  Are you struggling to communicate in English? We understand
                  that it can be difficult to speak naturally in a new language,
                  which is why we have developed an online course to help you
                  master the art of conversation in English. Our course is
                  designed for non-English speakers who want to expand their
                  vocabulary and communicate effectively in everyday situations,
                  whether it be making friends, conducting business, watching
                  English films, or traveling to an English-speaking country.
                </p>
                <p class="mt-2">
                  As the world's universal language, having a basic
                  understanding of English is essential for functioning in most
                  countries. However, our course will take your English skills
                  to the next level, enabling you to communicate like a native
                  and express even your most complex thoughts. Our comprehensive
                  curriculum covers all aspects of the English language,
                  including grammar, vocabulary, and pronunciation, with a focus
                  on real-life scenarios.
                </p>
                <p class="mt-2">
                  Upon completion of our course, you'll be able to navigate
                  through any English-speaking country with ease, connect with
                  locals and other travelers, conduct business, enroll in
                  classes, and so much more. We strive to make our course
                  accessible and easy to understand for non-English speakers, so
                  whether you're a beginner or an intermediate speaker, our
                  course will help you achieve your goals.
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
                    Non-native English speakers who want to improve their
                    fluency and pronunciation
                  </li>
                  <li>
                    English language learners who want to improve their
                    listening comprehension
                  </li>
                  <li>
                    Business professionals who want to improve their English
                    communication skills
                  </li>
                  <li>
                    Students who need to pass an English proficiency test for
                    academic or professional purposes
                  </li>
                  <li>
                    Anyone who wants to gain confidence speaking and listening
                    in English.
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
  <Guestfooter />
</template>

<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

const defaultValue = "item-1";

const accordionItems = [
  {
    value: "item-1",
    title: "Unit 1: Introduction to English language",
    content: [
      {
        value: "https://www.youtube.com/embed/xT0qms5poA8?si=SrAumfu7XLeH03dQ",
        label: "Lesson 1: Why learn English",
      },
      {
        value: "https://www.youtube.com/embed/ZqO0rrKbKO4?si=8k29Eix3NoDEfm6p",
        label: "Lesson 2: English Language Basics Part 1",
      },
      {
        value: "https://www.youtube.com/embed/rB6mnJTUppg?si=_gE6STxD-cRdJugo",
        label: "Lesson 3: English Language Basics Part 2",
      },
    ],
  },
  {
    value: "item-2",
    title: "Unit 2: Basic communication",
    content: [
      {
        value: "https://www.youtube.com/embed/xT0qms5poA8?si=SrAumfu7XLeH03dQ",
        label: "Lesson 1: Why learn English",
      },
      {
        value: "https://www.youtube.com/embed/ZqO0rrKbKO4?si=8k29Eix3NoDEfm6p",
        label: "Lesson 2: English Language Basics Part 1",
      },
      {
        value: "https://www.youtube.com/embed/rB6mnJTUppg?si=_gE6STxD-cRdJugo",
        label: "Lesson 3: English Language Basics Part 2",
      },
    ],
  },
  {
    value: "item-3",
    title: "Unit 3: Business communication",
    content: [
      {
        value: "https://www.youtube.com/embed/xT0qms5poA8?si=SrAumfu7XLeH03dQ",
        label: "Lesson 1: How to ask for and give directions in English",
      },
      {
        value: "https://www.youtube.com/embed/ZqO0rrKbKO4?si=8k29Eix3NoDEfm6p",
        label: "Lesson 2: How to order food in English",
      },
      {
        value: "https://www.youtube.com/embed/rB6mnJTUppg?si=_gE6STxD-cRdJugo",
        label: "Lesson 3: How to talk about hobbies and interests",
      },
    ],
  },
];

const selectedValue = ref(
  "https://www.youtube.com/embed/yYF2Vf1Gc14?si=o4MaabEp_FWPTcMn"
);

const handleItemClick = (value: string) => {
  console.log("Selected Item Value:", value);
  selectedValue.value = value;
};
</script>
