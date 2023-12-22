<template>
  <header class="bg-gray-800 text-white p-2 sticky top-0 shadow-xl z-50">
    <div
      class="container mx-auto flex flex-col-reverse sm:flex-row items-center justify-between"
    >
      <!-- navigation for mobile device -->
      <div
        class="xl:hidden lg:hidden md:hidden absolute top-[110px] right-2 bg-gray-800 text-black p-4 text-xl w-[100px] rounded-xl shadow-md"
        v-show="isNav"
      >
        <nav
          class="text-[14px] font-semibold text-gray-300 flex-1 justify-between"
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

        <!-- serach input box -->
        <div class="ml-2 flex items-center relative">
          <input
            type="text"
            placeholder="What do you want to learn?"
            class="bg-gray-700 text-white font-light text-xs px-4 xl:w-80 sm: w-[200px] py-2 rounded-sm focus:outline-none focus:shadow-outline"
          />
          <Icon
            name="material-symbols:search"
            class="absolute right-2 cursor-pointer sm:"
            color="white"
          />
        </div>
        <!-- menu for navigation -->
        <div class="block xl:hidden lg:hidden md:hidden" @click="showNav">
          <Icon
            name="material-symbols:menu"
            class="ml-2 cursor-pointer text-4xl"
            color="white"
          />
        </div>
      </div>
      <!-- Navigation header sections -->
      <nav
        class="text-[14px] font-semibold text-gray-300 w-[200px] justify-around items-center hidden lg:flex xl:flex"
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
      <!-- right side header sections -->
      <div class="flex mb-1">
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
        <div>
          <button
            @click="toggleStateTheme()"
            class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white px-4 py-2 ml-5"
          >
            <Icon
              v-if="!isDarkTheme"
              name="ph:sun-dim-light"
              class="cursor-pointer text-xl"
              color="white"
            />
            <Icon
              v-else
              name="ph:moon-stars-thin"
              class="cursor-pointer text-xl"
              color="white"
            />
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
const language = ref("አማ");
const isDropdownVisible = ref(false);
const isDarkTheme = ref(false);
const isNav = ref(false);

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

// function to handle navigation visiblity in mobile device
const showNav = () => {
  isNav.value = !isNav.value;
};
</script>
