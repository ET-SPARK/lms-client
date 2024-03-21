<template>
  <Header />
  <div class="px-4 mt-4 border mx-4 rounded-xl py-4" v-for="item in discussion">
    <div class="flex items-center">
      <Avatar class="rounded-full">
        <AvatarFallback>
          {{ item.role.split(" ")[0][0] }}
          {{ item.role.split(" ").pop()[0] }}</AvatarFallback
        >
      </Avatar>
      <div class="font-bold text-sm ml-2">{{ item.role }}</div>
    </div>
    <div>
      <div class="font-light text-sm text-justify">{{ item.message }}</div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { Avatar, AvatarFallback } from "@/components/ui/avatar";

const discussion = [
  {
    role: "Course Instructor",
    message:
      "Join us for an exciting web development workshop on March 20, 2024, from 10:00 AM to 12:00 PM, where we'll explore the fundamentals of HTML, CSS, and JavaScript. Whether you're a beginner or looking to brush up on your skills, this session is perfect for you. Get ready to dive into the world of web development and learn how to build your own websites from scratch. Zoom link:https://googlezom/sdsadjhjhkjshdkj/jujsyh",
  },
  {
    role: "Admin",
    message:
      "Join us for an advanced web development bootcamp on April 5, 2024, from 2:00 PM to 4:00 PM, where we'll delve deep into the intricacies of front-end and back-end development. Whether you're an experienced developer or aspiring to elevate your skills, this session is tailored for you. Prepare to immerse yourself in advanced topics such as responsive design, RESTful APIs, and database integration. Don't miss out on this opportunity to refine your expertise and take your projects to the next level. Zoom link: https://googlezom/sdsadjhjhkjshdkj/jujsyh",
  },
];
</script>
