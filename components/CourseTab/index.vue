<template>
  <Tabs default-value="account" class="w-full">
    <TabsList>
      <TabsTrigger value="about"> About </TabsTrigger>
      <TabsTrigger value="discussion"> Discussion </TabsTrigger>
      <TabsTrigger value="feedback"> Feedback </TabsTrigger>
    </TabsList>
    <TabsContent value="about"> <CourseTabAbout /> </TabsContent>
    <TabsContent value="discussion"><CourseTabDiscussion /> </TabsContent>
    <TabsContent value="feedback"><CourseTabFeedback /> </TabsContent>
  </Tabs>
</template>

<script setup lang="ts">
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";
</script>
