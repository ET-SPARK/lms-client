<template>
  <Carousel
    class="relative w-[400px] ml-20"
    :plugins="[plugin]"
    @mouseenter="plugin.stop"
    @mouseleave="[plugin.reset(), plugin.play(), console.log('Running')]"
  >
    <CarouselContent>
      <CarouselItem v-for="testimonial in testimonials" :key="testimonial.id">
        <div class="p-1">
          <Card>
            <CardContent
              class="flex items-center flex-col justify-between sm:px-6 mt-10"
            >
              <span class="mb-4 text-base text-center sm:mb-6">{{
                testimonial.text
              }}</span>
              <span class="mb-2 text-lg font-light mt-5">{{
                testimonial.author
              }}</span>
              <span class="mb-4 font-semibold uppercase md:self-center">{{
                testimonial.profession
              }}</span>
              <img
                :src="testimonial.image"
                class="testimonial-card-image w-12 h-12 object-cover rounded-full"
              />
            </CardContent>
          </Card>
        </div>
      </CarouselItem>
    </CarouselContent>
    <CarouselPrevious />
    <CarouselNext />
  </Carousel>
</template>

<script setup lang="ts">
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

const testimonials = [
  {
    id: 1,
    text: "I greatly improved my coding skills using the learning management system.",
    author: "John Doe",
    profession: "Software Engineer",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/06/portrait-square-02.jpg",
  },
  {
    id: 2,
    text: "The LMS provided me with valuable insights into data science concepts.",
    author: "Jane Smith",
    profession: "Data Scientist",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/03/portrait-square-06.jpg",
  },
  {
    id: 3,
    text: "I enhanced my project management skills through the learning management system.",
    author: "Michael Johnson",
    profession: "Project Manager",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/01/portraits-circle-small_6-1.png",
  },
  {
    id: 4,
    text: "The LMS played a crucial role in my journey to become a UX/UI designer.",
    author: "Emily Brown",
    profession: "UX/UI Designer",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/01/portraits-circle-small_1-1.png",
  },
  {
    id: 5,
    text: "I gained valuable knowledge in cybersecurity from the learning management system.",
    author: "David Williams",
    profession: "Cybersecurity Analyst",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/01/portraits-circle-small_2-1.png",
  },
  {
    id: 6,
    text: "The LMS helped me become proficient in machine learning and AI technologies.",
    author: "Sophia Rodriguez",
    profession: "Machine Learning Engineer",
    image:
      "https://www.elegantthemes.com/layouts/wp-content/uploads/2018/01/portraits-circle-small_5.png",
  },
];
</script>
