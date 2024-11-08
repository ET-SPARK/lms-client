<template>
  <footer
    class="dark:bg-background absolute bottom-0-0 pt-6 text-center w-full overflow-x-auto border-t-2"
  >
    <div class="mx-auto w-full max-w-screen-xl p-4 py-6 lg:py-8">
      <div class="md:flex md:justify-between">
        <div class="mb-6 md:mb-0 ml-10 sm:ml-1">
          <a href="https://andinetsolutions.com/" class="flex items-center">
            <img
              src="../../static/images/andinet_logo.jpg"
              class="h-12 sm:h-28 me-3 rounded-full"
              alt="Andinet lms logo"
            />
            <span class="self-center text-2xl font-semibold whitespace-nowrap"
              >Andinet Academy
            </span>
          </a>
        </div>
      </div>
      <hr
        class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8"
      />
      <div class="sm:flex sm:items-center sm:justify-between">
        <span class="text-l max-[600px]:text-sm sm:text-center"
          >© {{ currentYear }}
          <a href="https://andinetsolutions.com/" class="hover:underline"
            >Andinet Business Group</a
          >. All Rights Reserved.
        </span>
        <div class="flex justify-between py-8 mt-2">
          <div v-for="item in socialMediaIcons">
            <TooltipProvider>
              <Tooltip>
                <TooltipTrigger
                  ><Icon
                    :name="item.name"
                    class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
                /></TooltipTrigger>
                <TooltipContent>
                  <p>{{ item.tooltipContent }}</p>
                </TooltipContent>
              </Tooltip>
            </TooltipProvider>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from "@/components/ui/tooltip";
const currentYear = ref(new Date().getFullYear());

const socialMediaIcons = [
  {
    name: "tabler:brand-facebook",
    tooltipContent: "Facebook",
  },
  {
    name: "tabler:brand-instagram",
    tooltipContent: "Instagram",
  },
  {
    name: "tabler:brand-tiktok",
    tooltipContent: "TikTok",
  },
  {
    name: "pajamas:twitter",
    tooltipContent: "X (Twitter)",
  },
  {
    name: "tabler:brand-telegram",
    tooltipContent: "Telegram",
  },
  {
    name: "tabler:brand-youtube",
    tooltipContent: "YouTube",
  },
  {
    name: "tabler:brand-linkedin",
    tooltipContent: "LinkedIn",
  },
];
</script>
