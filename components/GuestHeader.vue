<template>
  <header class="bg-gray-800 text-white p-2 sticky top-0 shadow-xl z-50">
    <div class="container mx-auto flex items-center justify-between">
      <!-- left side header -->
      <div>
        <div class="text-2xl font-bold flex items-center">
          <!-- logo -->
          <div class="flex">
            <NuxtLink to="/" class="hover:text-gray-300">
              <img
                class="w-10 h-10 cursor-pointer rounded-full"
                src="../static/homeimage/andinet_logo.jpg"
              />
            </NuxtLink>
            <div class="ml-4">LMS</div>
          </div>

          <!-- on hover show list of course  -->
          <div
            class="xl:flex lg:hidden md:hidden sm: hidden relative flex text-[14px] font-semibold ml-2 text-gray-300"
            @mouseover="showDropdown"
            @mouseout="hideDropdown"
          >
            <div class="cursor-pointer py-2" @click="toggleDropdown">
              Courses
              <Icon
                v-if="!isDropdownVisible"
                name="material-symbols:arrow-drop-down"
                class="cursor-pointer text-3xl sm:text-xl"
                color="white"
              />
              <Icon
                v-if="isDropdownVisible"
                name="material-symbols:arrow-drop-up"
                class="cursor-pointer text-3xl sm:text-xl"
                color="white"
              />
            </div>
            <!-- all Categories course  -->
            <div
              v-show="isDropdownVisible"
              class="absolute bg-white text-black p-4 text-sm xl:w-[600px] sm: w-[320px] top-[50px] rounded-xl shadow-md"
            >
              <div class="flex1">
                <div class="flex justify-between mb-5">
                  <div class="text-lg">Categories</div>
                  <div class="text-sm text-blue-500 underline">
                    <NuxtLink to="/"> View all </NuxtLink>
                  </div>
                </div>

                <div class="flex-1 font-light border-gray-200 border-t-2">
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
              </div>
              <div
                class="flex justify-between mt-5 items-center bg-gray-100 p-4"
              >
                <div class="flex1">
                  <div>Get started</div>
                  <div class="font-light">
                    Discover a wide range of online courses in variety <br />
                    of fields to enhance your abilities and knowledge
                  </div>
                </div>
                <div>
                  <button class="cursor-pointer border bg-gray-300 px-4 py-2">
                    Get started
                  </button>
                </div>
              </div>
            </div>
          </div>

          <!-- serach input box -->
          <div
            class="ml-2 flex items-center relative xl:flex lg:hidden md:hidden sm: hidden"
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
            <NuxtLink to="/">
              <button
                class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-full"
              >
                Sign Up
              </button>
            </NuxtLink>
            <NuxtLink to="/">
              <button
                class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 rounded-full ml-6"
              >
                Log in
              </button>
            </NuxtLink>
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
  </header>

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
            <Icon name="ep:brush" class="cursor-pointer text-white text-2xl" />
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
      <NuxtLink to="/">
        <button
          class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 rounded-sm ml-6"
        >
          Log in
        </button>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const language = ref("አማ");
const isDropdownVisible = ref(false);
const isDarkTheme = ref(false);
const isNav = ref(false);
const isCourse = ref(false);

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// function to handle Course dropdown
const toggleDropdown = () => {
  isDropdownVisible.value = !isDropdownVisible.value;
};

// function to handle theme change
const toggleStateTheme = () => {
  isDarkTheme.value = isDarkTheme.value === false ? true : false;
};

// function to handle navigation visiblity menu in mobile & tab device
const showNav = () => {
  isNav.value = !isNav.value;
};

//handle course dropdown in mobile and tab screen
const toggleDropdownCourese = () => {
  isCourse.value = !isCourse.value;
};

// mouse hover show course Dropdown
const showDropdown = () => {
  isDropdownVisible.value = true;
};

// mouse hover remove course Dropdown
const hideDropdown = () => {
  isDropdownVisible.value = false;
};
</script>
