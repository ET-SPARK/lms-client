<template>
  <header
    class="py-1 sticky top-0 shadow-xl z-50 bg-white"
    :class="{ 'dark:bg-background': isDarkMode }"
  >
    <div class="container flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="flex items-center">
          <!-- logo -->
          <div class="flex items-center">
            <NuxtLink to="/" class="hover:text-gray-300">
              <img
                class="w-10 h-10 cursor-pointer rounded-full"
                src="../../../static/homeimage/andinet_logo.jpg"
              />
            </NuxtLink>
          </div>

          <!-- on hover show list of course  -->
          <div class="ml-2 xl:flex lg:flex md:flex sm: hidden">
            <NavCourseNav />
          </div>

          <!-- serach input box -->
          <div class="ml-2"><NavSearchNav /></div>
        </div>
      </div>
      <!-- navigation part -->
      <div class="xl:flex lg:hidden md:hidden sm: hidden">
        <div>
          <NavAuthMenu />
        </div>
      </div>

      <!-- Profile and language part -->
      <div>
        <div class="flex mb-1">
          <!-- profile part -->
          <div>
            <NavProfileNav />
          </div>
          <!-- used to change the language -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <Button
              @click="toggleStateLanguage()"
              variant="outline"
              class="px-4 py-2 ml-8"
            >
              {{ language }}
            </Button>
          </div>
          <!-- used to change the theme -->
          <div>
            <Button
              class="ml-2 max-[600px]:text-[12px]"
              :class="{ dark: isDarkMode }"
              @click="toggleDarkMode"
            >
              <Icon
                v-if="isDarkMode"
                name="material-symbols:light-mode-outline"
                class="bg-#212F3D cursor-pointer text-[20px] max-[600px]:text-[12px]"
              />
              <Icon
                v-else
                name="ph:moon-stars-light"
                class="bg-#212F3D cursor-pointer text-[20px] max-[600px]:text-[12px]"
              />
            </Button>
          </div>
          <!-- for mobile and tab screen navigation, search box, theme and language changing part -->
          <div>
            <Sheet>
              <SheetTrigger as-child>
                <Button
                  variant="outline"
                  class="xl:hidden bg-gray-800 boarder border-blue-500 hover:border-gray-800 text-blue-500 px-4 py-2 ml-2"
                >
                  <!-- menu navigation for mobile and tab screen -->
                  <div class="flex">
                    <Icon
                      name="material-symbols:menu"
                      class="cursor-pointer text-xl"
                    />
                  </div>
                </Button>
              </SheetTrigger>
              <div>
                <SheetContent
                  class="bg-gray-800 text-white font-semibold text-[12px]"
                >
                  <SheetHeader>
                    <!-- serach box -->
                    <div class="items-center flex mt-4 mb-2 justify-start">
                      <input
                        type="text"
                        placeholder="What do you want to learn?"
                        class="bg-gray-700 text-white font-light text-xs px-4 w-[300px] py-2 rounded-sm focus:outline-none focus:shadow-outline"
                      />
                      <div class="ml-1 bg-white py-1 px-1">
                        <!-- Use span instead of div for inline elements -->
                        <Icon
                          name="material-symbols:search"
                          class="cursor-pointer"
                          color="black"
                        />
                      </div>
                    </div>
                  </SheetHeader>

                  <!-- navigation links -->
                  <div class="mt-2">
                    <NuxtLink to="/">
                      <div
                        class="border-gray-200 border-b-2 p-2 hover:bg-gray-700"
                      >
                        Assignments<sup class="font-bold text-xl text-red-600"
                          >0</sup
                        >
                      </div>
                    </NuxtLink>
                    <NuxtLink to="/">
                      <div
                        class="border-gray-200 border-b-2 p-2 hover:bg-gray-700"
                      >
                        Discussions<sup class="font-bold text-xl text-red-600"
                          >0</sup
                        >
                      </div>
                    </NuxtLink>
                  </div>

                  <!-- course dropdown -->
                  <div
                    class="flex border-gray-200 border-b-2 p-2 cursor-pointer hover:bg-gray-700"
                    @click="toggleDropdownCourese"
                  >
                    <div class="cursor-pointe">Courses</div>
                    <div>
                      <Icon
                        v-if="isCourse"
                        name="material-symbols:arrow-drop-up"
                        class="cursor-pointer text-2xl"
                        color="white"
                      />
                      <Icon
                        v-else
                        name="material-symbols:arrow-drop-down"
                        class="cursor-pointer text-2xl"
                        color="white"
                      />
                    </div>
                  </div>

                  <!-- show all Categories course  -->
                  <div
                    class="flex-1 font-light mt-4 text-[10px]"
                    v-if="isCourse"
                  >
                    <NavMobCourseNav />
                  </div>

                  <div class="mt-4 flex">
                    <!-- language change button -->
                    <div class="flex mt-5">
                      <div>
                        <Button
                          @click="toggleStateLanguage()"
                          variant="outline"
                          class="bg-gray-800 border border-blue-500 hover:border-gray-800 text-blue-500 px-4 py-2 ml-8"
                        >
                          {{ language }}
                        </Button>
                      </div>
                    </div>
                  </div>
                </SheetContent>
              </div>
            </Sheet>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

import {
  Sheet,
  SheetContent,
  SheetHeader,
  SheetTrigger,
} from "@/components/ui/sheet";

const language = ref("አማ");
const isNav = ref(false);
const isCourse = ref(false);
const isDarkMode = ref(false);

// function to handle theme change
const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  const html = document.querySelector("html");
  html.classList.toggle("dark", isDarkMode.value);
};

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// function to handle navigation visibility menu in a mobile device
const showNav = () => {
  isNav.value = !isNav.value;
};

// handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};
</script>
