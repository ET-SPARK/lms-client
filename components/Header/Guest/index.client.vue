<template>
  <header
    class="py-1 sticky top-0 shadow-xl z-50 bg-white border border-b"
    :class="{ 'dark:bg-background': isDarkMode }"
  >
    <div class="container flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="flex items-center">
          <!-- mobile and tab screen dropdown part -->
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
                  <div>
                    <NuxtLink to="/">
                      <div class="border-b-2 p-2">Home</div>
                    </NuxtLink>
                    <NuxtLink to="/about">
                      <div class="border-b-2 p-2">About</div>
                    </NuxtLink>
                    <NuxtLink to="/contact">
                      <div class="border-b-2 p-2">Contact</div>
                    </NuxtLink>
                  </div>

                  <!-- course dropdown -->
                  <div
                    class="flex border-b-2 p-2 cursor-pointer"
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

                  <div class="mt-4 flex justify-around">
                    <AuthSignup />
                    <AuthLogin />
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
          <NavGuestMenu />
        </div>
      </div>

      <!-- signup, login, theme and language part -->
      <div>
        <div class="flex mb-1">
          <!-- Auth part -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <div>
              <AuthSignup />
            </div>
            <div>
              <AuthLogin />
            </div>
          </div>

          <!-- used to change language -->
          <div class="">
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

import {
  Sheet,
  SheetContent,
  SheetHeader,
  SheetTrigger,
} from "@/components/ui/sheet";

const language = ref("አማ");
const isCourse = ref(false);
const isDarkMode = ref(false);

// Function to handle theme change
const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  updateTheme(isDarkMode.value);
};

// Function to update theme
const updateTheme = (darkMode) => {
  const html = document.querySelector("html");
  html.classList.toggle("dark", darkMode);

  // Update localStorage based on user preference
  localStorage.theme = darkMode ? "dark" : "light";
};

// On page load, check localStorage for theme preference
onMounted(() => {
  const storedTheme = localStorage.theme;

  if (
    storedTheme === "dark" ||
    (!storedTheme && window.matchMedia("(prefers-color-scheme: dark)").matches)
  ) {
    isDarkMode.value = true;
  }

  // Apply the initial theme
  updateTheme(isDarkMode.value);
});
// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};
</script>
