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
        <NavigationMenuTrigger class=""> Courses </NavigationMenuTrigger>
        <NavigationMenuContent>
          <div class="text-[14px] pb-6">
            <div class="flex justify-between mt-4 mb-2 px-10">
              <div class="">Categories</div>
              <div class="text-sm hover:text-blue-500 underline">
                <NuxtLink to="/courses"> View all </NuxtLink>
              </div>
            </div>
            <ul
              class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px] border-t-2"
            >
              <li
                class="cursor-pointer"
                v-for="course in courseNavList"
                :key="course.icon"
              >
                <NuxtLink to="/">
                  <div
                    class="flex items-center hover:text-blue-500 cursor-pointer"
                  >
                    <div class="p-1 mr-2 rounded-md">
                      <Icon :name="course.icon" class="text-2xl" />
                    </div>
                    <div>{{ course.name }}</div>
                  </div>
                </NuxtLink>
              </li>
            </ul>
          </div>
        </NavigationMenuContent>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
