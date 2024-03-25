<template>
  <header
    class="py-1 sticky top-0 shadow-xl z-50 bg-background border border-b"
  >
    <div class="container flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="flex items-center">
          <!-- for mobile and tab screen navigation, search box, theme and language changing part -->
          <div>
            <Sheet>
              <SheetTrigger as-child>
                <Button variant="outline" class="xl:hidden py-2">
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
                        <NuxtLink to="/home" class="flex items-center">
                          <div class="mr-2">
                            <img
                              class="w-10 h-10 cursor-pointer rounded-full"
                              src="../../../static/homeimage/andinet_logo.jpg"
                            />
                          </div>
                          <div class="font-bold">Andinet Academy</div>
                        </NuxtLink>
                      </div>
                    </div>
                  </SheetHeader>

                  <!-- navigation links -->
                  <div>
                    <NuxtLink to="/home">
                      <div class="border-b-2 p-2">Home</div>
                    </NuxtLink>
                    <NuxtLink to="/courses">
                      <div class="border-b-2 p-2">Courses</div>
                    </NuxtLink>
                    <NuxtLink to="/about">
                      <div class="border-b-2 p-2">About</div>
                    </NuxtLink>
                    <NuxtLink to="/contact">
                      <div class="border-b-2 p-2">Contact</div>
                    </NuxtLink>
                  </div>

                  <!-- navigation part -->
                  <div class="xl:flex lg:hidden md:hidden sm: hidden">
                    <div>
                      <NavGuestMenu />
                    </div>
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
            <NuxtLink to="/home" class="flex items-center">
              <div class="mr-2">
                <img
                  class="w-10 h-10 cursor-pointer rounded-full"
                  src="../../../static/homeimage/andinet_logo.jpg"
                />
              </div>
              <div class="font-bold">Andinet Academy</div>
            </NuxtLink>
          </div>
        </div>
      </div>

      <!-- navigation part -->
      <div class="xl:flex lg:hidden md:hidden sm: hidden">
        <div>
          <NavGuestMenu />
        </div>
      </div>

      <!-- Profile and language part -->
      <div>
        <div class="flex mb-1">
          <!-- profile part -->
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
          <div class="ml-2">
            <DropdownMenu>
              <DropdownMenuTrigger as-child>
                <Button variant="outline">
                  <Icon
                    :name="
                      colorMode.preference === 'light'
                        ? 'ph:moon-stars-light'
                        : 'material-symbols:light-mode-outline'
                    "
                    class="cursor-pointer text-[20px] max-[600px]:text-[12px]"
                  />
                  <span class="sr-only">Toggle theme</span>
                </Button>
              </DropdownMenuTrigger>
              <DropdownMenuContent align="end">
                <DropdownMenuItem @click="colorMode.preference = 'light'">
                  Light
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'dark'">
                  Dark
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'system'">
                  System
                </DropdownMenuItem>
              </DropdownMenuContent>
            </DropdownMenu>
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
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";

const colorMode = useColorMode();

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};
</script>
