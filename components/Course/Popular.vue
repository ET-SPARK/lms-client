<template>
  <p class="text-xl font-bold my-4 ml-16 max-[640px]:text-sm">
    Most Popular Course
  </p>

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
                class="flex items-center flex-col justify-between sm:px-6 mt-2 h-[450px]"
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
                    <p class="text-sm">{{ course.description }}</p>
                  </div>
                  <div class="ml-2 py-2 text-sm">{{ course.reward }}</div>
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

const courseLists = [
  {
    id: 1,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/4b/bca2a4dc43408497819f5b976e14e9/302050841.jpeg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Cloud Computing",
    logo: "http://coursera-university-assets.s3.amazonaws.com/a4/7cd68a658840ddbb95c38cdd0bbc8e/aws-logo-icon-PNG-Transparent-Background.png",
    title: "Amazon Web Service",
    description: "AWS Cloud Technology Consultant",
    reward: "Professional Certificate",
  },
  {
    id: 2,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://coursera-course-photos.s3.amazonaws.com/85/25cdfb95114467b047ce901ee5b3c7/ESL_CourseLogo.jpg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Data Science",
    logo: "http://coursera-university-assets.s3.amazonaws.com/3a/043acda9fb458194d1cbcd38ca6d5c/Rice_Logo_280_Blue_Square.png",
    title: "Data Science Fundamentals",
    description: "Introduction to Data Science",
    reward: "Data Science Certificate",
  },
  {
    id: 3,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/a4/0ee0209fb444a38ade1afccde6355e/option2.jpg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Web Development",
    logo: "http://coursera-university-assets.s3.amazonaws.com/0e/4bb2b81f8e453eab147bbb94bb53da/Intuit_Square_360x360_WhiteonBlue.png",
    title: "Full Stack Web Development",
    description: "Master the art of web development",
    reward: "Web Development Certification",
  },
  {
    id: 4,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://s3.amazonaws.com/coursera_assets/ddp/branding/mads-umich/construction-engineering-management-umich-banner.jpg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Machine Learning",
    logo: "http://coursera-university-assets.s3.amazonaws.com/cc/61dbdf2c1c475d82d3b8bf8eee1bda/MSFT-stacked-logo_FINAL.png",
    title: "Machine Learning Basics",
    description: "Explore the world of machine learning",
    reward: "Machine Learning Certificate",
  },
  {
    id: 5,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/83/27c0906c9b11e697217132e89362f6/CM_SpecLogo800.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Cybersecurity",
    logo: "http://coursera-university-assets.s3.amazonaws.com/2f/8bf130459a11e78f3f93ee93db5719/cu_collegiate_blue.png",
    title: "Cybersecurity Essentials",
    description: "Enhance your skills in cybersecurity",
    reward: "Cybersecurity Certification",
  },
  {
    id: 6,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/61/edc4c8538e49fd97efecab1665e969/GenAI_Logo-Image_1200x1200pxl-copy.jpg?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Artificial Intelligence",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/bb/f5ced2bdd4437aa79f00eb1bf7fbf0/IBM-Logo-Blk---Square.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Introduction to AI",
    description: "Understanding Artificial Intelligence",
    reward: "AI Certificate",
  },
  {
    id: 7,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/8c/e0f2fd124b441fa8d9aa68fdab2167/Marketing-Image.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&fit=crop&q=50",
    category: "Digital Marketing",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/b4/5cb90bb92f420b99bf323a0356f451/Icon.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Digital Marketing Fundamentals",
    description: "Mastering Digital Marketing",
    reward: "Digital Marketing Certificate",
  },
  {
    id: 8,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/da/507477bbb74db4b7f98d1d50f15cbb/IBM-DW-Eng-PC-Coursera-Final-1-.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&q=50&fit=crop",
    category: "Graphic Design",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/bb/f5ced2bdd4437aa79f00eb1bf7fbf0/IBM-Logo-Blk---Square.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Graphic Design Essentials",
    description: "Creating Stunning Designs",
    reward: "Graphic Design Certificate",
  },
  {
    id: 9,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/9a/a0d7131af944ebbc335e2f60409e6e/specialization_-CFA-Institute-Data-Science-for-Investment.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&q=50&fit=crop",
    category: "Mobile App Development",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/1e/b944bdb16247cb977a54eb8860f5e9/cfa-logo-360-min.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Mobile App Development Basics",
    description: "Building Mobile Apps",
    reward: "Mobile App Development Certificate",
  },
  {
    id: 10,
    badge: "Latest",
    image:
      "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://d15cw65ipctsrr.cloudfront.net/64/e9c91436254d768b5ddb328579b536/DevOps_PC_Image_Final.png?auto=format%2Ccompress%2C%20enhance&dpr=1&w=265&h=204&q=50&fit=crop",
    category: "Blockchain",
    logo: "https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/http://coursera-university-assets.s3.amazonaws.com/73/e03b13a8e44df9b19eb279e5506396/360-x-360.png?auto=format%2Ccompress&dpr=1&w=25&h=25&q=40",
    title: "Introduction to Blockchain",
    description: "Exploring Blockchain Technology",
    reward: "Blockchain Certificate",
  },
];
</script>
import type { Course } from "#build/components";import type { NuxtLink } from
"#build/components";
