<template>
  <Header />
  <div class="mx-24 mt-10 text-4xl font-bold max-[640px]:text-[26px]">
    My Courses
  </div>
  <div class="border mx-24 my-10 max-[640px]:m-8">
    <div class="border p-4 m-4">
      <div>Completed Courses (0)</div>
      <div>In Progress (2)</div>
    </div>
    <div class="text-2xl max-[640px]:text-xl font-bold mt-10 px-8">
      Continue learning
    </div>
    <NuxtLink to="/courseVideo">
      <div class="flex justify-between border p-4 m-4 max-[820px]:flex-col">
        <div class="flex items-center max-[640px]:flex-col">
          <div class="relative">
            <Icon
              name="material-symbols:play-arrow"
              class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black cursor-pointer text-white text-[24px] rounded-full bg-opacity-60"
            />
            <img
              src="https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg"
              class="w-40 h-24"
            />
          </div>
          <div class="ml-4 max-[640px]:mt-2 max-[820px]:border-l-0">
            <div class="font-light max-[640px]:text-sm">Course | Language</div>
            <div class="text-xl max-[640px]:text-[18px]">
              English for career development
            </div>
            <div class="flex items-center">
              <Progress v-model="progress" class="w-3/5 h-[8px]" />
              <div class="mt-2 ml-4">60%</div>
            </div>
            <div class="font-light text-sm">Course: <Badge>Active</Badge></div>
          </div>
        </div>
        <div
          class="w-1/2 border-l max-[820px]:border-l-0 max-[820px]:border-t max-[820px]:mt-4 max-[820px]:w-full max-[820px]:pt-4"
        >
          <div class="ml-4 max-[820px]:ml-0">
            <div class="flex justify-between items-center mb-2">
              <div>Next Up</div>
              <div>
                <DropdownMenu>
                  <DropdownMenuTrigger>
                    <Icon
                      name="ph:dots-three-outline-vertical-fill"
                      class="text-xl"
                    />
                  </DropdownMenuTrigger>
                  <DropdownMenuContent>
                    <DropdownMenuItem>Unenroll</DropdownMenuItem>
                    <DropdownMenuSeparator />
                    <DropdownMenuItem>Progress</DropdownMenuItem>
                    <DropdownMenuSeparator />
                    <DropdownMenuItem>Get Certificate</DropdownMenuItem>
                  </DropdownMenuContent>
                </DropdownMenu>
              </div>
            </div>
            <div class="font-semibold">Introduction to Communication</div>
            <div class="font-light text-sm">Chapter 3 | Lesson 2</div>
          </div>
        </div>
      </div>
    </NuxtLink>
    <div class="flex justify-between border p-4 m-4 max-[820px]:flex-col">
      <div class="flex items-center max-[640px]:flex-col">
        <div class="relative">
          <Icon
            name="material-symbols:play-arrow"
            class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black cursor-pointer text-white text-[24px] rounded-full bg-opacity-60"
          />
          <img
            src="https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg"
            class="w-40 h-24"
          />
        </div>
        <div class="ml-4 max-[640px]:mt-2 max-[820px]:border-l-0">
          <div class="font-light max-[640px]:text-sm">Course | Language</div>
          <div class="text-xl max-[640px]:text-[18px]">
            English for career development
          </div>
          <div class="font-light text-sm">Course: <Badge>Inactive</Badge></div>
        </div>
      </div>
      <div
        class="w-1/2 border-l max-[820px]:border-l-0 max-[820px]:border-t max-[820px]:mt-4 max-[820px]:w-full max-[820px]:pt-4"
      >
        <div class="ml-4 max-[820px]:ml-0">
          <div class="flex justify-between items-center mb-2">
            <div>Next Up</div>
            <div>
              <DropdownMenu>
                <DropdownMenuTrigger>
                  <Icon
                    name="ph:dots-three-outline-vertical-fill"
                    class="text-xl"
                  />
                </DropdownMenuTrigger>
                <DropdownMenuContent>
                  <DropdownMenuItem>Unenroll</DropdownMenuItem>
                </DropdownMenuContent>
              </DropdownMenu>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>

<script setup lang="ts">
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";

import { ref, watchEffect } from "vue";
import { Progress } from "@/components/ui/progress";

const progress = ref(13);

watchEffect((cleanupFn) => {
  const timer = setTimeout(() => (progress.value = 66), 500);
  cleanupFn(() => clearTimeout(timer));
});
</script>
import type { Progress } from "#build/components";
