<script setup lang="ts">
import { Menubar, MenubarMenu, MenubarTrigger } from "@/components/ui/menubar";
</script>

<template>
  <Menubar>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/">Assignments</NuxtLink>
      </MenubarTrigger>
    </MenubarMenu>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/">Discussions</NuxtLink>
      </MenubarTrigger>
    </MenubarMenu>
  </Menubar>
</template>
