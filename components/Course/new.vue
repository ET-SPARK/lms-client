<template>
  <p class="text-xl font-bold my-4 ml-16 max-[640px]:text-sm">New Courses</p>
  <div
    class="grid grid-cols-3 h-[450px] max-[640px]:h-auto mx-16 mt-4 gap-6 max-[640px]:grid-cols-1 max-[820px]:grid-cols-2"
    v-if="courseLists.length === 0"
  >
    <div v-for="index in repeatCount" :key="index">
      <div class="w-full border rounded-2xl p-6">
        <div class="p-2 relative">
          <div class="absolute mt-1 right-4">
            <Skeleton class="h-4 w-[50px] ml-2" />
          </div>
          <Skeleton class="h-[225px] max-[640px]:h-[150px] w-full rounded-xl" />
        </div>
        <div class="h-[120px] ml-2 mr-2 border-b">
          <Skeleton class="h-4 w-[150px]" />
          <div class="flex items-center mt-2">
            <Skeleton class="w-8 h-8 rounded-full" />
            <Skeleton class="h-4 w-[150px] ml-2" />
          </div>
          <div class="py-2">
            <Skeleton class="h-4 w-full mt-2" />
            <Skeleton class="h-4 w-full mt-2" />
          </div>
        </div>
        <Skeleton class="h-4 w-[150px] mt-4 ml-2" />
      </div>
    </div>
  </div>
  <Carousel
    class="relative mx-16 mt-4"
    :plugins="[plugin]"
    @mouseenter="plugin.stop"
    @mouseleave="[plugin.reset(), plugin.play(), console.log('Running')]"
  >
    <CarouselContent>
      <CarouselItem
        v-for="course in courseLists"
        :key="course.id"
        class="md:basis-1/2 lg:basis-1/3"
      >
        <NuxtLink to="/courseDetail">
          <div class="p-1 max-[640px]:text-[12px]">
            <Card>
              <CardContent
                class="flex items-center flex-col justify-between mt-2 h-[450px] max-[640px]:h-auto"
              >
                <div class="w-full">
                  <div class="p-2 relative">
                    <div class="absolute mt-1 right-4">
                      <Badge>{{ course.badge }}</Badge>
                    </div>
                    <img class="rounded-xl w-full" :src="course.image" />
                  </div>
                  <div class="h-[120px] ml-2 mr-2 border-b">
                    <p class="text-sm mb-2">{{ course.category }}</p>
                    <div class="flex items-center">
                      <img
                        class="w-8 h-8 rounded-full border"
                        :src="course.logo"
                      />
                      <p class="text-[12px] ml-2 font-light">
                        {{ course.title }}
                      </p>
                    </div>
                    <p class="text-[12px]">{{ course.description }}</p>
                  </div>
                  <div class="ml-2 py-2 text-12px">{{ course.reward }}</div>
                </div>
              </CardContent>
            </Card>
          </div>
        </NuxtLink>
      </CarouselItem>
    </CarouselContent>
    <CarouselPrevious />
    <CarouselNext />
  </Carousel>
</template>

<script setup lang="ts">
import { Badge } from "@/components/ui/badge";
import Autoplay from "embla-carousel-autoplay";
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";
import { Card, CardContent } from "@/components/ui/card";

const plugin = Autoplay({
  delay: 2000,
  stopOnMouseEnter: true,
  stopOnInteraction: false,
});

const repeatCount = ref(3);
const courseLists = [
  {
    id: 1,
    badge: "New",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/83/27c0906c9b11e697217132e89362f6/CM_SpecLogo800.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Cybersecurity",
    logo: "http://coursera-university-assets.s3.amazonaws.com/2f/8bf130459a11e78f3f93ee93db5719/cu_collegiate_blue.png",
    title: "Cybersecurity Essentials",
    description: "Enhance your skills in cybersecurity",
    reward: "Cybersecurity Certification",
  },
  {
    id: 2,
    badge: "New",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/61/edc4c8538e49fd97efecab1665e969/GenAI_Logo-Image_1200x1200pxl-copy.jpg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Artificial Intelligence",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/bb/f5ced2bdd4437aa79f00eb1bf7fbf0/IBM-Logo-Blk---Square.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Introduction to AI",
    description: "Understanding Artificial Intelligence",
    reward: "AI Certificate",
  },
  {
    id: 3,
    badge: "New",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/8c/e0f2fd124b441fa8d9aa68fdab2167/Marketing-Image.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Digital Marketing",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/b4/5cb90bb92f420b99bf323a0356f451/Icon.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Digital Marketing Fundamentals",
    description: "Mastering Digital Marketing",
    reward: "Digital Marketing Certificate",
  },
  {
    id: 4,
    badge: "New",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/da/507477bbb74db4b7f98d1d50f15cbb/IBM-DW-Eng-PC-Coursera-Final-1-.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&q=50&fit=crop",
    category: "Graphic Design",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/bb/f5ced2bdd4437aa79f00eb1bf7fbf0/IBM-Logo-Blk---Square.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Graphic Design Essentials",
    description: "Creating Stunning Designs",
    reward: "Graphic Design Certificate",
  },
  {
    id: 5,
    badge: "New",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/9a/a0d7131af944ebbc335e2f60409e6e/specialization_-CFA-Institute-Data-Science-for-Investment.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&q=50&fit=crop",
    category: "Mobile App Development",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/1e/b944bdb16247cb977a54eb8860f5e9/cfa-logo-360-min.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Mobile App Development Basics",
    description: "Building Mobile Apps",
    reward: "Mobile App Development Certificate",
  },
];
</script>
