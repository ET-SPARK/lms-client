<script setup lang="ts">
import { Menubar, MenubarMenu, MenubarTrigger } from "@/components/ui/menubar";
</script>

<template>
  <Menubar>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/home">Home</NuxtLink>
      </MenubarTrigger>
    </MenubarMenu>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/courses">Courses</NuxtLink></MenubarTrigger
      >
    </MenubarMenu>
    <MenubarMenu>
      <MenubarTrigger><NuxtLink to="/about">About</NuxtLink></MenubarTrigger>
    </MenubarMenu>
    <MenubarMenu>
      <MenubarTrigger>
        <NuxtLink to="/contact">Contact</NuxtLink></MenubarTrigger
      >
    </MenubarMenu>
  </Menubar>
</template>
