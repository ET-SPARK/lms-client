<template>
  <HeaderAuth />
  <div class="p-2 bg-gray-200">
    <section class="flex1 w-full my-10">
      <div>
        <div class="flex justify-between max-[1024px]:flex-col">
          <div>
            <!-- video player -->
            <div>
              <div class="video-section">
                <div>
                  <div class="relative">
                    <iframe
                      width="100%"
                      height="400"
                      :src="`${selectedValue}`"
                      class="rounded-2xl"
                      title="YouTube video player"
                      frameborder="0"
                      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                      allowfullscreen
                    ></iframe>
                  </div>
                </div>
              </div>
            </div>
            <!-- course detail  -->
            <div class="flex1 bg-gray-200 mt-2">
              <div>
                <div class="p-4">
                  <!-- cource title -->
                  <div>
                    <p class="text-2xl font-bold max-[600px]:text-[16px]">
                      {{ selectedTitle }} <br />
                      {{ selectedLabel }}
                    </p>
                  </div>
                  <!-- profile -->
                  <div class="flex items-center justify-between">
                    <div class="flex items-center">
                      <div class="mt-4">
                        <Avatar>
                          <AvatarImage
                            src="https://github.com/radix-vue.png"
                            alt="@radix-vue"
                          />
                          <AvatarFallback>S</AvatarFallback>
                        </Avatar>
                      </div>
                      <NuxtLink to="#">
                        <div
                          class="ml-5 text-gray-500 hover:text-blue-500 max-[600px]:text-[12px]"
                        >
                          <div>
                            A course by <br />
                            Abebe
                          </div>
                        </div>
                      </NuxtLink>
                    </div>
                    <div class="flex">
                      <div class="mr-2">
                        <Badge>
                          <Icon
                            name="bx:bxs-like"
                            class="text-2xl max-[600px]:text-[16px]"
                          />
                        </Badge>
                      </div>
                      <div>
                        <Badge>
                          <Icon
                            name="mdi:share"
                            class="text-2xl max-[600px]:text-[16px]"
                          />
                        </Badge>
                      </div>
                    </div>
                  </div>
                  <div>
                    <p
                      class="text-2xl font-bold mt-2 max-[600px]:text-[16px] ml-14"
                    >
                      About the Course
                    </p>
                  </div>
                </div>
                <!-- course detail discription -->
                <div class="px-4 text-justify ml-14">
                  <div class="max-[600px]:text-[12px]">
                    <p class="mt-1">
                      Are you struggling to communicate in English? We
                      understand that it can be difficult to speak naturally in
                      a new language, which is why we have developed an online
                      course to help you master the art of conversation in
                      English. Our course is designed for non-English speakers
                      who want to expand their vocabulary and communicate
                      effectively in everyday situations, whether it be making
                      friends, conducting business, watching English films, or
                      traveling to an English-speaking country.
                    </p>
                    <p class="mt-2">
                      As the world's universal language, having a basic
                      understanding of English is essential for functioning in
                      most countries. However, our course will take your English
                      skills to the next level, enabling you to communicate like
                      a native and express even your most complex thoughts. Our
                      comprehensive curriculum covers all aspects of the English
                      language, including grammar, vocabulary, and
                      pronunciation, with a focus on real-life scenarios.
                    </p>
                    <p class="mt-2">
                      Upon completion of our course, you'll be able to navigate
                      through any English-speaking country with ease, connect
                      with locals and other travelers, conduct business, enroll
                      in classes, and so much more. We strive to make our course
                      accessible and easy to understand for non-English
                      speakers, so whether you're a beginner or an intermediate
                      speaker, our course will help you achieve your goals.
                    </p>
                  </div>
                  <p class="text-2xl font-bold max-[600px]:text-[16px]">
                    Requirements
                  </p>
                  <div class="max-[600px]:text-[12px]">
                    <ul class="mt-2 list-disc ml-10">
                      <li>Basic understanding of computers and the internet</li>
                      <li>
                        Familiarity with social media platforms (helpful, but
                        not required)
                      </li>
                      <li>
                        Access to a computer or mobile device with a stable
                        internet connection
                      </li>
                    </ul>
                  </div>
                  <p class="mt-2 text-2xl font-bold max-[600px]:text-[16px]">
                    Who is this course for?
                  </p>
                  <div class="max-[600px]:text-[12px]">
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
                        Students who need to pass an English proficiency test
                        for academic or professional purposes
                      </li>
                      <li>
                        Anyone who wants to gain confidence speaking and
                        listening in English.
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- course play list -->
          <div class="px-4 bg-gray-200 w-full">
            <div class="mb-4">
              <span class="font-bold text-2xl max-[600px]:text-[16px]"
                >Contents</span
              >
            </div>
            <div class="bg-white p-4">
              <Accordion
                type="single"
                class="w-full text-start items-start max-[600px]:text-[12px]"
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
                        class="p-2 max-[600px]:text-[12px]"
                      >
                        <div
                          class="cursor-pointer"
                          @click="
                            handleItemClick(
                              contentItem.value,
                              contentItem.label,
                              item.title
                            )
                          "
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
import { Badge } from "@/components/ui/badge";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

const defaultValue = "item-1";

const accordionItems = [
  {
    value: "item-1",
    title: "Unit 1: Introduction to English language",
    content: [
      {
        value: "https://www.youtube.com/embed/tIwnRkmHNvc?si=VGHhTUQS-4PA1-HX",
        label: "Lesson 1: Why learn English",
      },
      {
        value: "https://www.youtube.com/embed/SaBH_huiJSM?si=i9jforwwyN0DHLdt",
        label: "Lesson 2: English Language Basics Part 1",
      },
      {
        value: "https://www.youtube.com/embed/cB7vltnJsOw?si=PpjSDeBEd2DvTEtS",
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
        value: "https://www.youtube.com/embed/kjR-3_ctBMA?si=4E2Jg6i1ifv8KTEz",
        label: "Lesson 1: How to ask for and give directions in English",
      },
      {
        value: "https://www.youtube.com/embed/kjR-3_ctBMA?si=27SRf5oDq0OhxDGM",
        label: "Lesson 2: How to order food in English",
      },
      {
        value: "https://www.youtube.com/embed/h-Np7dmvw0U?si=LRSOEJY13RcaJH96",
        label: "Lesson 3: How to talk about hobbies and interests",
      },
    ],
  },
];

const selectedValue = ref(
  "https://www.youtube.com/embed/yYF2Vf1Gc14?si=o4MaabEp_FWPTcMn"
);
const selectedTitle = ref("Unit 1: Introduction to English language");
const selectedLabel = ref("Lesson 1: Why learn English");

const handleItemClick = (value: string, label: string, title: string) => {
  selectedValue.value = value;
  selectedLabel.value = label;
  selectedTitle.value = title;
};
</script>
