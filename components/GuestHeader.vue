<template>
  <header class="bg-gray-800 text-white p-2 sticky top-0 shadow-xl z-50">
    <div class="container mx-auto flex items-center justify-between">
      <!-- Left side header sections -->
      <div class="text-2xl font-bold flex items-center">
        <div>
          <NuxtLink to="/" class="hover:text-gray-300">
            <img
              class="w-10 h-10 cursor-pointer rounded-full"
              src="../static/homeimage/andinet_logo.jpg"
            />
          </NuxtLink>
        </div>
        <!-- on click show list of course  -->
        <div class="relative flex text-[14px] font-semibold ml-5 text-gray-300">
          <div class="cursor-pointer" @click="toggleDropdown">
            Courses
            <Icon
              name="material-symbols:arrow-drop-down"
              class="cursor-pointer text-3xl"
              color="white"
            />
          </div>
          <!-- all Categories course  -->
          <div
            v-show="isDropdownVisible"
            class="absolute bg-white text-black p-4 text-sm w-[600px] top-[50px] rounded-xl shadow-md"
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
            <div class="flex justify-between mt-5 items-center bg-gray-100 p-4">
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
        <div class="ml-5 flex items-center relative">
          <input
            type="text"
            placeholder="What do you want to learn?"
            class="bg-gray-700 text-white font-light text-xs px-4 w-80 py-2 rounded-sm focus:outline-none focus:shadow-outline"
          />
          <Icon
            name="material-symbols:search"
            class="absolute right-2 cursor-pointer"
            color="white"
          />
        </div>
      </div>
      <!-- right side header sections -->
      <div class="flex">
        <!-- profile part -->
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
        <!-- used to change the language -->
        <div>
          <button
            @click="toggleStateLanguage()"
            class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 ml-10"
          >
            {{ language }}
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
const language = ref("አማ");
const isDropdownVisible = ref(false);
const isProfileVisible = ref(false);

// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};

// function to handle Course dropdown
const toggleDropdown = () => {
  isDropdownVisible.value = !isDropdownVisible.value;
};
</script>
