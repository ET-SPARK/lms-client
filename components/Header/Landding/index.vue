<template>
  <header class="py-1 sticky top-0 shadow-xl z-50 bg-background border-b">
    <div class="container flex items-center justify-between">
      <NuxtLink to="/" class="flex items-center">
        <div class="mr-2">
          <img
            class="w-10 h-10 cursor-pointer rounded-full"
            src="../../../static/homeimage/andinet_logo.jpg"
          />
        </div>
        <div class="font-bold">Andinet Academy</div>
      </NuxtLink>

      <!-- Profile and language part -->
      <div>
        <div class="flex mb-1 items-center">
          <!-- used to change the language -->
          <div class="xl:flex lg:hidden md:hidden sm: hidden">
            <Button
              @click="toggleStateLanguage()"
              variant="outline"
              class="px-4 py-2 ml-8"
            >
              {{ language }}
            </Button>
          </div>
          <!-- used to change the theme -->
          <div class="ml-2">
            <DropdownMenu>
              <DropdownMenuTrigger as-child>
                <Button variant="outline">
                  <Icon
                    :name="
                      colorMode.preference === 'light'
                        ? 'ph:moon-stars-light'
                        : 'material-symbols:light-mode-outline'
                    "
                    class="cursor-pointer text-[20px] max-[600px]:text-[12px]"
                  />
                  <span class="sr-only">Toggle theme</span>
                </Button>
              </DropdownMenuTrigger>
              <DropdownMenuContent align="end">
                <DropdownMenuItem @click="colorMode.preference = 'light'">
                  Light
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'dark'">
                  Dark
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'system'">
                  System
                </DropdownMenuItem>
              </DropdownMenuContent>
            </DropdownMenu>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
import { Button } from "@/components/ui/button";
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";
const colorMode = useColorMode();
const language = ref("አማ");
// function to handle language change
const toggleStateLanguage = () => {
  language.value = language.value === "አማ" ? "En" : "አማ";
};
</script>
