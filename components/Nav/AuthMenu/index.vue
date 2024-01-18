<script setup lang="ts">
import { Menubar, MenubarMenu, MenubarTrigger } from "@/components/ui/menubar";
</script>

<template>
  <Menubar>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/"
          >Assignments<sup class="font-bold text-xl text-red-600"
            >0</sup
          ></NuxtLink
        >
      </MenubarTrigger>
    </MenubarMenu>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/"
          >Discussions<sup class="font-bold text-xl text-red-600"
            >0</sup
          ></NuxtLink
        >
      </MenubarTrigger>
    </MenubarMenu>
  </Menubar>
</template>
