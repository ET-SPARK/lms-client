<template>
  <div class="px-4 mt-4 border mx-4 rounded-xl py-4" v-for="item in discussion">
    <div class="flex items-center">
      <Avatar class="rounded-full">
        <AvatarFallback>
          {{ item.studentName.split(" ")[0][0] }}
          {{ item.studentName.split(" ").pop()[0] }}</AvatarFallback
        >
      </Avatar>
      <div class="font-bold text-sm ml-2">{{ item.studentName }}</div>
    </div>
    <div>
      <div class="font-light text-sm">{{ item.message }}</div>
    </div>
  </div>
  <div class="px-4 sticky bottom-0 my-4 w-full">
    <div class="relative">
      <Icon name="bi:send-fill" class="absolute right-2 text-2xl top-2" />
      <Textarea placeholder="Type your message here." />
    </div>
  </div>
</template>
<script setup lang="ts">
import { Avatar, AvatarFallback } from "@/components/ui/avatar";
import { Textarea } from "@/components/ui/textarea";

const discussion = [
  {
    studentName: "David Smith",
    message:
      "Just started a web dev course. It's awesome! Learning HTML, CSS, JS. Can't wait to create cool stuff!",
  },
  {
    studentName: "Sarah Thompson",
    message:
      "Learning web dev. HTML, CSS, JS - check! Instructors rock. Excited to build amazing websites!",
  },
  {
    studentName: "John Davis",
    message:
      "Started web dev course. HTML, CSS, JS basics down. Loving the journey. Can't wait to see what's next!",
  },
  {
    studentName: "Jessica Brown",
    message:
      "Taking a web dev course. HTML, CSS, JS are fascinating. Instructors are supportive. Ready to code!",
  },
  {
    studentName: "Daniel Wilson",
    message:
      "Joined a web dev course. HTML, CSS, JS learning mode on! Instructors are fantastic. Excited to create!",
  },
  {
    studentName: "Sophie Miller",
    message:
      "Enrolled in web dev course. HTML, CSS, JS are my new best friends! Instructors are amazing. Ready to build!",
  },
  {
    studentName: "Ryan Clark",
    message:
      "Started web dev journey. HTML, CSS, JS are intriguing. Instructors are top-notch. Can't wait to code!",
  },
  {
    studentName: "Olivia Harris",
    message:
      "Learning web dev. HTML, CSS, JS - loving it! Instructors are supportive. Excited to create websites!",
  },
  {
    studentName: "Ethan Walker",
    message:
      "Taking a web dev course. HTML, CSS, JS are fascinating. Instructors are awesome. Ready to build cool stuff!",
  },
  {
    studentName: "Grace Martin",
    message:
      "Joined web dev course. HTML, CSS, JS are mind-blowing! Instructors are great. Excited to craft websites!",
  },
];
</script>
