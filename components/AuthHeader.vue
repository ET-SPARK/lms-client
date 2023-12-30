<template>
  <header class="bg-gray-800 text-white py-2 sticky top-0 shadow-xl z-50">
    <div class="container mx-auto flex items-center justify-between">
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
            <div class="ml-2">LMS</div>
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
            <div>
              Assignments<sup class="font-bold text-xl text-red-600">0</sup>
            </div>
          </NuxtLink>
          <NuxtLink to="/">
            <div>
              Discussions<sup class="font-bold text-xl text-red-600">0</sup>
            </div>
          </NuxtLink>
        </nav>
      </div>

      <!-- Profile and language part -->
      <div>
        <div class="flex mb-1">
          <!-- profile part -->
          <div>
            <DropdownMenu>
              <DropdownMenuTrigger>
                <Icon
                  name="material-symbols:account-circle-outline"
                  class="cursor-pointer text-4xl rounded-sm"
                  color="white"
              /></DropdownMenuTrigger>
              <DropdownMenuContent class="px-4">
                <DropdownMenuLabel>My Account</DropdownMenuLabel>
                <DropdownMenuSeparator />
                <DropdownMenuItem>
                  <div
                    class="flex items-center mb-2 border-b-2 border-gray-300 pb-4"
                  >
                    <div>
                      <Icon
                        name="streamline:interface-favorite-award-ribbon-reward-like-social-rating-media"
                        class="cursor-pointer ml-1 text-xl rounded-sm mr-2"
                        color="black"
                      />
                    </div>
                    <div>My course</div>
                  </div>
                </DropdownMenuItem>
                <DropdownMenuItem>
                  <div class="flex items-center mb-2">
                    <div>
                      <Icon
                        name="material-symbols:person-outline"
                        class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                        color="black"
                      />
                    </div>
                    <div>Profile</div>
                  </div>
                </DropdownMenuItem>
                <DropdownMenuItem>
                  <div class="flex items-center mb-2">
                    <div>
                      <Icon
                        name="material-symbols:circle-notifications-outline"
                        class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                        color="black"
                      />
                    </div>
                    <div>Notifications</div>
                  </div>
                </DropdownMenuItem>
                <DropdownMenuItem
                  ><div class="flex items-center mb-2">
                    <div>
                      <Icon
                        name="material-symbols:android-messages-outline"
                        class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                        color="black"
                      />
                    </div>
                    <div>Messages</div>
                  </div>
                </DropdownMenuItem>
                <DropdownMenuItem>
                  <div class="flex items-center mb-2">
                    <div>
                      <Icon
                        name="material-symbols:settings"
                        class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                        color="black"
                      />
                    </div>
                    <div>Settings</div>
                  </div>
                </DropdownMenuItem>
                <DropdownMenuItem>
                  <div class="flex items-center mb-2">
                    <div>
                      <Icon
                        name="clarity:sign-out-line"
                        class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                        color="black"
                      />
                    </div>
                    <div>Log out</div>
                  </div>
                </DropdownMenuItem>
              </DropdownMenuContent>
            </DropdownMenu>
          </div>
          <!-- used to change the language -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <Button
              @click="toggleStateLanguage()"
              variant="outline"
              class="bg-gray-800 border border-blue-500 hover:border-gray-800 text-blue-500 px-4 py-2 ml-8"
            >
              {{ language }}
            </Button>
          </div>

          <!-- menu for navigation for mobile and tab screen -->
          <div class="flex xl:hidden" @click="showNav">
            <Icon
              v-if="isNav"
              name="material-symbols:close-rounded"
              class="ml-2 cursor-pointer text-4xl"
              color="white"
            />
            <Icon
              v-else
              name="material-symbols:menu"
              class="ml-2 cursor-pointer text-4xl"
              color="white"
            />
          </div>
        </div>
      </div>
    </div>
    <!-- for mobile and tab screen navigation, search box, theme and language changing part -->
    <div
      class="font-semibold bg-gray-800 items-center text-white p-4 xl:hidden z-50"
      v-if="isNav"
    >
      <!-- serach box   -->
      <div class="items-center flex mt-5 mb-2 justify-start">
        <input
          type="text"
          placeholder="What do you want to learn?"
          class="bg-gray-700 text-white font-light text-xs px-4 w-[300px] py-2 rounded-sm focus:outline-none focus:shadow-outline"
        />
        <div class="ml-1 bg-white py-1 px-1">
          <Icon
            name="material-symbols:search"
            class="cursor-pointer"
            color="black"
          />
        </div>
      </div>

      <!-- navigation  -->
      <NuxtLink to="/">
        <div class="border-gray-200 border-b-2 py-2">
          Assignments<sup class="font-bold text-xl text-red-600">0</sup>
        </div>
      </NuxtLink>
      <NuxtLink to="/">
        <div class="border-gray-200 border-b-2 py-2">
          Discussions<sup class="font-bold text-xl text-red-600">0</sup>
        </div>
      </NuxtLink>

      <!-- course dropdown -->
      <div
        class="flex border-gray-200 border-b-2 py-2 cursor-pointer"
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

      <!-- on click show list of course  -->
      <div class="flex-1 font-light mt-4" v-if="isCourse">
        <div class="grid grid-cols-2 gap-5 justify-between mt-4 mb-4">
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
  </header>
</template>

<script setup>
import { ref } from "vue";
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";

const language = ref("አማ");
const isNav = ref(false);
const isCourse = ref(false);

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
