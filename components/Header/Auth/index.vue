<template>
  <header
    class="py-1 sticky top-0 shadow-xl z-50 bg-white border border-b"
    :class="{ 'dark:bg-background': isDarkMode }"
  >
    <div class="container flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="flex items-center">
          <!-- for mobile and tab screen navigation, search box, theme and language changing part -->
          <div>
            <Sheet>
              <SheetTrigger as-child>
                <Button variant="outline" class="xl:hidden px-4 py-2 ml-2">
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
                <SheetContent class="font-semibold text-[12px]">
                  <SheetHeader>
                    <div class="flex items-center">
                      <!-- logo -->
                      <div class="flex">
                        <NuxtLink to="/" class="mr-2">
                          <img
                            class="w-10 h-10 cursor-pointer rounded-full"
                            src="../../../static/homeimage/andinet_logo.jpg"
                          />
                        </NuxtLink>
                      </div>
                      <!-- serach box -->
                      <div class="items-center flex mt-4 mb-2 justify-start">
                        <NavSearchNav />
                      </div>
                    </div>
                  </SheetHeader>

                  <!-- navigation links -->
                  <div class="mt-2">
                    <NuxtLink to="/">
                      <div class="border-b-2 p-2">Assignments</div>
                    </NuxtLink>
                    <NuxtLink to="/">
                      <div class="border-b-2 p-2">Discussions</div>
                    </NuxtLink>
                  </div>

                  <!-- course dropdown -->
                  <div
                    class="flex border-gray-200 border-b-2 p-2 cursor-pointer"
                    @click="toggleDropdownCourese"
                  >
                    <div class="cursor-pointe">Courses</div>
                    <div>
                      <Icon
                        v-if="isCourse"
                        name="material-symbols:arrow-drop-up"
                        class="cursor-pointer text-2xl"
                      />
                      <Icon
                        v-else
                        name="material-symbols:arrow-drop-down"
                        class="cursor-pointer text-2xl"
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

                  <div class="mt-4 flex items-center">
                    <!-- language change button -->
                    <div class="flex">
                      <div>
                        <Button
                          @click="toggleStateLanguage()"
                          variant="outline"
                          class="px-4 py-2 ml-8"
                        >
                          {{ language }}
                        </Button>
                      </div>
                    </div>
                    <!-- used to change the theme -->
                  </div>
                </SheetContent>
              </div>
            </Sheet>
          </div>
          <!-- logo -->
          <div
            class="flex items-center max-[1280px]:hidden max-[1024px]:hidden max-[768px]:hidden max-[640px]:hidden"
          >
            <NuxtLink to="/" class="">
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
          <div
            class="ml-2 flex items-center relative xl:flex lg:flex md:flex sm: hidden"
          >
            <NavSearchNav />
          </div>
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
