<template>
  <header class="bg-gray-800 text-white p-2 sticky top-0 shadow-xl z-50">
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
          <NuxtLink to="/">
            <div>Contact</div>
          </NuxtLink>
        </nav>
      </div>

      <!-- signup, login, theme and language part -->
      <div>
        <div class="flex mb-1">
          <!-- Auth part -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <NuxtLink to="">
              <button
                class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-sm"
              >
                Sign Up
              </button>
            </NuxtLink>
            <div @click="showLogin()">
              <button
                class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 rounded-sm ml-6"
              >
                Log in
              </button>
            </div>
          </div>

          <!-- used to change language -->
          <div class="">
            <button
              @click="toggleStateLanguage()"
              class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 ml-10"
            >
              {{ language }}
            </button>
          </div>

          <!-- menu navigation for mobile and tab screen -->
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
    <!-- mobile and tab screen dropdown part -->
    <div
      class="font-semibold bg-gray-800 items-center text-white p-4 xl:hidden"
      v-if="isNav"
    >
      <!-- serach box -->
      <div class="items-center flex mt-5 mb-2 justify-start">
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

      <!-- navigation links -->
      <NuxtLink to="/">
        <div class="border-gray-200 border-b-2 py-2">Home</div>
      </NuxtLink>
      <NuxtLink to="/">
        <div class="border-gray-200 border-b-2 py-2">About</div>
      </NuxtLink>
      <NuxtLink to="/">
        <div class="border-gray-200 border-b-2 py-2">Contact</div>
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
      <!-- show all Categories course  -->
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

      <!-- auth part for mobile -->
      <div class="flex justify-around mt-5">
        <NuxtLink to="/">
          <button
            class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-sm"
          >
            Sign Up
          </button>
        </NuxtLink>
        <div @click="showLogin">
          <button
            class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 rounded-sm ml-6"
          >
            Log in
          </button>
        </div>
      </div>
    </div>
  </header>
  <div>
    <div
      class="fixed top-16 bottom-0 left-0 right-0 flex justify-center modal-overlay bg-black bg-opacity-60 z-50"
      v-if="isLogin"
    >
      <div
        class="text-center bg-white h-[600px] my-2 px-16 rounded-lg modal relative"
      >
        <Icon
          name="material-symbols:close-small"
          class="text-black text-4xl cursor-pointer absolute top-4 right-4"
          @click="showLogin"
        />
        <div class="font-semibold text-2xl mt-28">Good to see you again!</div>
        <form class="mt-12">
          <div class="flex1 text-start">
            <div class="mb-4">
              <label
                for="phoneNumber"
                class="block text-sm font-medium text-gray-700"
                >Phone Number</label
              >
              <div class="relative">
                <Icon
                  name="material-symbols:smartphone"
                  class="absolute inset-y-0 left-0 pl-2 mt-2 text-gray-500 text-3xl"
                />
                <input
                  v-model="phoneNumber"
                  type="tel"
                  id="phoneNumber"
                  name="phoneNumber"
                  class="pl-10 mt-1 p-2 border rounded-md w-full"
                  placeholder="Enter your phone number"
                  required
                />
              </div>
            </div>
            <div class="mb-4">
              <label
                for="password"
                class="block text-sm font-medium text-gray-700"
                >Password</label
              >
              <div class="relative">
                <Icon
                  name="mynaui:lock-password"
                  class="absolute inset-y-0 left-0 pl-2 mt-2 text-gray-500 text-3xl"
                />
                <Icon
                  v-if="showPassword"
                  @click="togglePasswordVisibility"
                  name="material-symbols:visibility-lock"
                  class="absolute inset-y-0 right-0 pr-2 mt-2 text-gray-500 text-3xl"
                />
                <Icon
                  v-else
                  @click="togglePasswordVisibility"
                  name="material-symbols:visibility"
                  class="absolute inset-y-0 right-0 pr-2 mt-2 text-gray-500 text-3xl cursor-pointer"
                />
                <input
                  :type="showPassword ? 'text' : 'password'"
                  id="password"
                  name="password"
                  class="pl-10 mt-1 p-2 border rounded-md w-full"
                  placeholder="Enter your password"
                  required
                />
              </div>
            </div>
          </div>
          <div class="mt-10">
            <button
              type="submit"
              class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-sm"
            >
              Log in
            </button>
            <div>or</div>
            <button
              type="submit"
              class="hover:bg-gray-100 text-black border px-4 py-2 rounded-sm flex justify-between items-center w-[250px] mt-4"
            >
              <div>
                <img src="../static/images/google.svg" class="w-6 h-6" />
              </div>
              <div class="">Continue with Google</div>
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const language = ref("አማ");
const isNav = ref(false);
const isCourse = ref(false);
const showPassword = ref(false);
const isLogin = ref(false);

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// function to handle navigation visibility menu in mobile & tab device
const showNav = () => {
  isNav.value = !isNav.value;
};

// handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};

const showLogin = () => {
  isLogin.value = !isLogin.value;
};

// toggle password visibility
const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
</script>
