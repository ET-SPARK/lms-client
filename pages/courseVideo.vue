<template>
  <Header />
  <div class="p-2">
    <section class="flex1 w-full my-10">
      <div class="lg:mr-4 md:mr-4 max-[640px]:mr-4">
        <div class="flex justify-between max-[1024px]:flex-col">
          <div class="xl:mr-4 w-2/3 max-[1024px]:w-full">
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
            <div class="flex1 mt-2">
              <div>
                <div class="p-4">
                  <!-- cource title -->
                  <div>
                    <p class="text-2xl font-bold max-[600px]:text-[16px]">
                      {{ selectedTitle }}
                    </p>
                    <p class="ml-4 text-2xl font-bold max-[600px]:text-[16px]">
                      {{ selectedLabel }}
                    </p>
                  </div>
                </div>
                <!-- profile -->
                <div
                  class="flex items-center justify-between border p-2 rounded-2xl my-4 ml-4"
                >
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
                        class="ml-5 hover:text-blue-500 max-[600px]:text-[12px]"
                      >
                        <div>Abebe</div>
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

                <!-- course detail discription -->
                <div class="text-justify ml-4 p-4 rounded-2xl border">
                  <CourseTab />
                </div>
              </div>
            </div>
          </div>
          <!-- course play list -->
          <div
            class="px-4 border ml-2 rounded-2xl max-[1024px]:mt-4 max-[768px]:mt-4 max-[640px]:mt-4 w-1/3 max-[1024px]:w-full"
          >
            <div>
              <div class="font-bold mb-2">Course Progress</div>
              <div>
                <div class="">
                  <Progress v-model="progress" class="h-[10px]" />
                  <div class="text-[12px]">24/32 Lessons</div>
                </div>
              </div>
              <div class="mt-2">
                <Progress v-model="pointprogress" class="h-[10px]" />
                <div class="text-[12px]">50/100 point</div>
              </div>
            </div>
            <div class="mt-4">
              <span class="font-bold text-2xl max-[600px]:text-[16px]"
                >Contents</span
              >
            </div>
            <div>
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
                  <AccordionContent class="border p-2 mb-2 rounded-xl">
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

                    <Dialog>
                      <DialogTrigger>
                        <Button>Take a Quiz</Button></DialogTrigger
                      >
                      <DialogContent>
                        <DialogHeader>
                          <DialogTitle>{{ item.title }} Quiz</DialogTitle>
                          <DialogDescription>
                            <Quiz />
                          </DialogDescription>
                        </DialogHeader>
                        <DialogClose>
                          <DialogFooter>
                            <Button>Close the quiz</Button>
                          </DialogFooter>
                        </DialogClose>
                      </DialogContent>
                    </Dialog>
                  </AccordionContent>
                </AccordionItem>
              </Accordion>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
  <Footer />
</template>

<script setup lang="ts">
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from "@/components/ui/dialog";
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

import { ref, watchEffect } from "vue";
import { Progress } from "@/components/ui/progress";

const progress = ref(13);
const pointprogress = ref(13);

watchEffect((cleanupFn) => {
  const timer = setTimeout(() => (progress.value = 75), 500);
  cleanupFn(() => clearTimeout(timer));
});

watchEffect((cleanupFn) => {
  const pointTimer = setTimeout(() => (pointprogress.value = 50), 500);
  cleanupFn(() => clearTimeout(pointTimer));
});
</script>
