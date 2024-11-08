<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

const defaultValue = "item-1";

const accordionItems = [
  {
    value: "item-1",
    title: "What is adinet LMS?",
    content:
      "Adinet LMS is an innovative full-service learning platform that produces, markets, and manages online courses in a variety of fields.",
  },
  {
    value: "item-2",
    title: "What kind of courses do you offer?",
    content:
      "Adinet LMS offers a diverse range of skill courses encompassing photography, graphic design, fashion design, music production, entrepreneurship, interior design, guitar playing, cake baking, nail art, lash extensions, and more.",
  },
  {
    value: "item-3",
    title: "What are the technical requirements for learning at Andinet LMS?",
    content:
      "To use Andinet LMS one needs to have a smartphone or computer and an internet access",
  },
];
</script>

<template>
  <Header />
  <div class="m-10 border p-10">
    <div class="mb-4 text-4xl font-bold max-[640px]:text-[26px]">FAQ</div>
    <Accordion
      type="single"
      class="w-full mt-10 mb-10 max-[640px]:text-sm"
      collapsible
      :default-value="defaultValue"
    >
      <AccordionItem
        v-for="item in accordionItems"
        :key="item.value"
        :value="item.value"
      >
        <AccordionTrigger>{{ item.title }}</AccordionTrigger>
        <AccordionContent class="font-light">
          {{ item.content }}
        </AccordionContent>
      </AccordionItem>
    </Accordion>
  </div>
  <Footer />
</template>
