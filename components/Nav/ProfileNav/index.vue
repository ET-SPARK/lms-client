<template>
  <div>
    <DropdownMenu>
      <DropdownMenuTrigger>
        <Avatar>
          <AvatarImage src="https://github.com/shadcn.png" alt="@radix-vue" />
          <AvatarFallback>S</AvatarFallback>
        </Avatar>
      </DropdownMenuTrigger>
      <DropdownMenuContent class="px-1">
        <DropdownMenuLabel>My Account</DropdownMenuLabel>
        <DropdownMenuSeparator />
        <DropdownMenuItem>
          <NuxtLink to="/profile">
            <div class="flex items-center mb-2">
              <div>
                <Icon
                  name="material-symbols:person-outline"
                  class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                />
              </div>
              <div>Profile</div>
            </div>
          </NuxtLink>
        </DropdownMenuItem>
        <DropdownMenuSeparator />
        <DropdownMenuItem>
          <NuxtLink to="/mycourse">
            <div class="flex items-center mb-2">
              <div>
                <Icon
                  name="streamline:interface-favorite-award-ribbon-reward-like-social-rating-media"
                  class="cursor-pointer ml-1 text-xl rounded-sm mr-2"
                />
              </div>
              <div>My course</div>
            </div>
          </NuxtLink>
        </DropdownMenuItem>
        <DropdownMenuSeparator />
        <DropdownMenuItem>
          <NuxtLink to="/messages">
            <div class="flex items-center mb-2">
              <div>
                <Icon
                  name="material-symbols:android-messages-outline"
                  class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                />
              </div>
              <div>Messages</div>
            </div>
          </NuxtLink>
        </DropdownMenuItem>
        <DropdownMenuSeparator />
        <DropdownMenuItem>
          <NuxtLink to="/">
            <div class="flex items-center mb-2">
              <div>
                <Icon
                  name="clarity:sign-out-line"
                  class="cursor-pointer ml-1 mr-2 text-xl rounded-sm"
                />
              </div>
              <div>Log out</div>
            </div>
          </NuxtLink>
        </DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  </div>
</template>

<script setup>
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
</script>
import type { NuxtLink } from "#build/components";
