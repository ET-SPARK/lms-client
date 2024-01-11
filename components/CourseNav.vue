<script setup lang="ts">
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle,
} from "@/components/ui/navigation-menu";

const courseNavList = [
  {
    icon: "streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting",
    name: "Accounting & Finance",
  },
  {
    icon: "ep:brush",
    name: "Art & Crafts",
  },
  {
    icon: "mdi:brush-off",
    name: "Beauty & Makeup",
  },
  {
    icon: "material-symbols:ink-pen-sharp",
    name: "Creatives & Design",
  },
  {
    icon: "ic:round-fastfood",
    name: "Food & Beverage",
  },
  {
    icon: "material-symbols:ecg-heart-outline",
    name: "Health & Fitness",
  },
  {
    icon: "streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit",
    name: "Business & Marketing",
  },
  {
    icon: "ph:code-bold",
    name: "IT & Development",
  },
  {
    icon: "lucide:languages",
    name: "Language & Literature",
  },
  {
    icon: "guidance:office",
    name: "Office productivity",
  },
  {
    icon: "guidance:meeting-point",
    name: "Personal development",
  },
  {
    icon: "material-symbols:camera",
    name: "Photography & Videography",
  },
];
</script>

<template>
  <NavigationMenu>
    <NavigationMenuList>
      <NavigationMenuItem>
        <NavigationMenuTrigger class="bg-gray-800">
          Courses
        </NavigationMenuTrigger>
        <NavigationMenuContent>
          <div class="text-[14px]">
            <div class="flex justify-between mt-4 mb-2 px-10">
              <div class="">Categories</div>
              <div class="text-sm text-blue-500 underline">
                <NuxtLink to="/"> View all </NuxtLink>
              </div>
            </div>
            <ul
              class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px] border-gray-200 border-t-2"
            >
              <li
                class="cursor-pointer"
                v-for="course in courseNavList"
                :key="course.icon"
              >
                <NuxtLink to="/">
                  <div class="flex items-center">
                    <div class="bg-blue-500 p-1 mr-2 rounded-md">
                      <Icon
                        :name="course.icon"
                        class="cursor-pointer text-white text-2xl"
                      />
                    </div>
                    <div>{{ course.name }}</div>
                  </div>
                </NuxtLink>
              </li>
            </ul>

            <div class="flex justify-between items-center bg-gray-100 p-6">
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
        </NavigationMenuContent>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
