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
    categorie: "accounting",
  },
  {
    icon: "ep:brush",
    name: "Art & Crafts",
    categorie: "art",
  },
  {
    icon: "mdi:brush-off",
    name: "Beauty & Makeup",
    categorie: "beauty",
  },
  {
    icon: "material-symbols:ink-pen-sharp",
    name: "Creatives & Design",
    categorie: "creatives",
  },
  {
    icon: "ic:round-fastfood",
    name: "Food & Beverage",
    categorie: "food",
  },
  {
    icon: "material-symbols:ecg-heart-outline",
    name: "Health & Fitness",
    categorie: "health",
  },
  {
    icon: "streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit",
    name: "Business & Marketing",
    categorie: "business",
  },
  {
    icon: "ph:code-bold",
    name: "IT & Development",
    categorie: "it",
  },
  {
    icon: "lucide:languages",
    name: "Language & Literature",
    categorie: "language",
  },
  {
    icon: "guidance:office",
    name: "Office Productivity",
    categorie: "office",
  },
  {
    icon: "guidance:meeting-point",
    name: "Personal Development",
    categorie: "personal",
  },
  {
    icon: "material-symbols:camera",
    name: "Photography & Videography",
    categorie: "photography",
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
              class="grid w-[400px] gap-3 p-4 md:w-[600px] md:grid-cols-3 lg:w-[800px] border-t-2"
            >
              <li
                class="cursor-pointer border-b"
                v-for="course in courseNavList"
                :key="course.icon"
              >
                <NuxtLink
                  :to="{
                    path: '/courses',
                    query: { categorie: course.categorie },
                  }"
                >
                  <NavCourseNavList
                    :name="course.name"
                    :icon="course.icon"
                  ></NavCourseNavList>
                </NuxtLink>
              </li>
            </ul>
          </div>
        </NavigationMenuContent>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
