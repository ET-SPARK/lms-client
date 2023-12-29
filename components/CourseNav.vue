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
</script>

<template>
  <NavigationMenu>
    <NavigationMenuList>
      <NavigationMenuItem>
        <NavigationMenuTrigger class="bg-gray-800">
          Courses</NavigationMenuTrigger
        >
        <NavigationMenuContent>
          <div>
            <div class="flex justify-between mt-4 mb-2 px-10">
              <div class="text-lg">Categories</div>
              <div class="text-sm text-blue-500 underline">
                <NuxtLink to="/"> View all </NuxtLink>
              </div>
            </div>
            <ul
              class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px] border-gray-200 border-t-2"
            >
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Accounting & Finance</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="ep:brush"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Art & Crafts</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="mdi:brush-off"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Beauty & Makeup</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="material-symbols:ink-pen-sharp"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Creatives & Design</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="ic:round-fastfood"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Food & Beverage</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="material-symbols:ecg-heart-outline"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Health & Fitness</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Business & Marketing</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="ph:code-bold"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>IT & Development</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="lucide:languages"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Language & Literature</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="ph:music-notes-fill"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Music & Theater</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="guidance:office"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Office productivity</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="guidance:meeting-point"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Personal development</div>
                </div>
              </li>
              <li>
                <div class="flex items-center">
                  <div class="bg-blue-500 p-1 mr-2 rounded-md">
                    <Icon
                      name="material-symbols:camera"
                      class="cursor-pointer text-white text-2xl"
                    />
                  </div>
                  <div>Photography & Videography</div>
                </div>
              </li>
            </ul>
            <div class="flex justify-between mt-2 items-center bg-gray-100 p-6">
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
