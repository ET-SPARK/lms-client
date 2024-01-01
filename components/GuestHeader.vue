<template>
  <header class="bg-gray-800 text-white p-2 sticky top-0 shadow-xl z-50">
    <div class="container flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="flex items-center">
          <!-- logo -->
          <div class="flex items-center">
            <NuxtLink to="/" class="hover:text-gray-300">
              <img
                class="w-10 h-10 cursor-pointer rounded-full"
                src="../static/homeimage/andinet_logo.jpg"
              />
            </NuxtLink>
            <div class="ml-4">LMS</div>
          </div>

          <!-- on hover show list of course  -->
          <div class="ml-2 xl:flex lg:flex md:flex sm: hidden">
            <CourseNav />
          </div>

          <!-- serach input box -->
          <div
            class="ml-2 flex items-center relative xl:flex lg:flex md:flex sm: hidden"
          >
            <input
              type="text"
              placeholder="What do you want to learn?"
              class="bg-gray-700 text-white font-light text-xs px-4 w-[300px] py-2 rounded-sm focus:outline-none focus:shadow-outline"
            />
            <Icon
              name="material-symbols:search"
              class="absolute right-2 cursor-pointer"
              color="white"
            />
          </div>
        </div>
      </div>

      <!-- navigation part -->
      <div class="xl:flex lg:hidden md:hidden sm: hidden">
        <nav
          class="text-[14px] font-semibold text-gray-300 w-[200px] justify-around items-center flex"
        >
          <NuxtLink to="/">
            <div>Home</div>
          </NuxtLink>
          <NuxtLink to="/">
            <div>About</div>
          </NuxtLink>
          <NuxtLink to="/contact">
            <div>Contact</div>
          </NuxtLink>
        </nav>
      </div>

      <!-- signup, login, theme and language part -->
      <div>
        <div class="flex mb-1">
          <!-- Auth part -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <div>
              <Signup />
            </div>
            <div>
              <Login />
            </div>
          </div>

          <!-- used to change language -->
          <div class="">
            <Button
              @click="toggleStateLanguage()"
              variant="outline"
              class="bg-gray-800 border border-blue-500 hover:border-gray-800 text-blue-500 px-4 py-2 ml-8"
            >
              {{ language }}
            </Button>
          </div>

          <!-- mobile and tab screen dropdown part -->
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
                        Home
                      </div>
                    </NuxtLink>
                    <NuxtLink to="/">
                      <div
                        class="border-gray-200 border-b-2 p-2 hover:bg-gray-700"
                      >
                        About
                      </div>
                    </NuxtLink>
                    <NuxtLink to="/contact">
                      <div
                        class="border-gray-200 border-b-2 p-2 hover:bg-gray-700"
                      >
                        Contact
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
                    <div
                      class="grid grid-cols-2 gap-5 justify-between mt-4 mb-4"
                    >
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Accounting & Finance</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="ep:brush"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Art & Crafts</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="mdi:brush-off"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Beauty & Makeup</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="material-symbols:ink-pen-sharp"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Creatives & Design</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="ic:round-fastfood"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Food & Beverage</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="material-symbols:ecg-heart-outline"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Health & Fitness</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Business & Marketing</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="ph:code-bold"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>IT & Development</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="lucide:languages"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Language & Literature</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="ph:music-notes-fill"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Music & Theater</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="guidance:office"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Office productivity</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="guidance:meeting-point"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Personal development</div>
                      </div>
                      <div class="flex items-center">
                        <div class="bg-blue-500 p-1 mr-2 rounded-md">
                          <Icon
                            name="material-symbols:camera"
                            class="cursor-pointer text-white text-2xl"
                          />
                        </div>
                        <div>Photography & Videography</div>
                      </div>
                    </div>
                  </div>

                  <div class="mt-4 flex justify-around">
                    <Signup />
                    <Login />
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
const isCourse = ref(false);

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};
</script>
