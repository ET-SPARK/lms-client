<template>
  <HeaderGuest />
  <div class="grid grid-cols-2 items-center">
    <div class="w-[300px]">
      <div class="mb-4 text-end">
        <Button class="px-6 py-4 text-xl font-light">
          <Icon name="material-symbols:filter-alt-off-rounded" class="mr-4" />
          Filter
        </Button>
      </div>
      <div>
        <div>
          <Accordion type="single" collapsible>
            <AccordionItem value="item-1">
              <AccordionTrigger
                class="justify-start hover:no-underline py-1 text-xl"
                >Category</AccordionTrigger
              >
              <AccordionContent>
                <div
                  class="flex items-center space-x-2 my-2"
                  v-for="item in courseCategories"
                  :key="item.categorie"
                >
                  <Checkbox id="terms" />
                  <label
                    for="terms"
                    class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
                  >
                    {{ item.name }}
                  </label>
                </div>
              </AccordionContent>
            </AccordionItem>
          </Accordion>
        </div>
        <div>
          <Accordion type="single" collapsible>
            <AccordionItem value="item-1">
              <AccordionTrigger
                class="justify-start hover:no-underline py-1 text-xl"
                >Video Duration</AccordionTrigger
              >
              <AccordionContent>
                <div
                  class="flex items-center space-x-2 my-2"
                  v-for="item in courseDuration"
                  :key="item.duration"
                >
                  <Checkbox id="terms" />
                  <label
                    for="terms"
                    class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
                  >
                    {{ item.duration }}
                  </label>
                </div>
              </AccordionContent>
            </AccordionItem>
          </Accordion>
        </div>
        <div>
          <Accordion type="single" collapsible>
            <AccordionItem value="item-1">
              <AccordionTrigger
                class="justify-start hover:no-underline py-1 text-xl"
                >Level</AccordionTrigger
              >
              <AccordionContent>
                <div
                  class="flex items-center space-x-2 my-2"
                  v-for="item in courseLevel"
                  :key="item.level"
                >
                  <Checkbox id="terms" />
                  <label
                    for="terms"
                    class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70"
                  >
                    {{ item.level }}
                  </label>
                </div>
              </AccordionContent>
            </AccordionItem>
          </Accordion>
        </div>
      </div>
    </div>
    <div class="h-full">
      <div class="font-semibold text-end text-md">"" results</div>
      <div>course part</div>
    </div>
  </div>
  <FooterGuest />
</template>

<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";
const course = [
  {
    courseId: "c001",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Introduction to Vue.js",
    lecturer: "John Doe",
    description: "Learn the basics of Vue.js framework.",
    level: "beginner",
    duration: "4:00 h",
    lessons: 12,
    badge: "New",
  },
  {
    courseId: "c002",
    category: "Business",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Business Analytics",
    lecturer: "Alice Johnson",
    description: "Explore the world of business analytics.",
    level: "intermediate",
    duration: "5:30 h",
    lessons: 15,
    badge: "Intermediate Badge",
  },
  {
    courseId: "c003",
    category: "Design",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Graphic Design Fundamentals",
    lecturer: "Eva Martinez",
    description: "Master the fundamentals of graphic design.",
    level: "advanced",
    duration: "6:45 h",
    lessons: 20,
    badge: "Advanced Badge",
  },
];
const courseCategories = [
  {
    name: "Accounting & Finance",
    categorie: "accounting",
  },
  {
    name: "Art & Crafts",
    categorie: "art",
  },
  {
    name: "Beauty & Makeup",
    categorie: "beauty",
  },
  {
    name: "Creatives & Design",
    categorie: "creatives",
  },
  {
    name: "Food & Beverage",
    categorie: "food",
  },
  {
    name: "Health & Fitness",
    categorie: "health",
  },
  {
    name: "Business & Marketing",
    categorie: "business",
  },
  {
    name: "IT & Development",
    categorie: "it",
  },
  {
    name: "Language & Literature",
    categorie: "language",
  },
  {
    name: "Office Productivity",
    categorie: "office",
  },
  {
    name: "Personal Development",
    categorie: "personal",
  },
  {
    name: "Photography & Videography",
    categorie: "photography",
  },
];
const courseDuration = [
  {
    duration: "0-1 Hour",
  },
  {
    duration: "1-3 Hours",
  },
  {
    duration: "3-6 Hours",
  },
  {
    duration: "6-18 Hours",
  },
  {
    duration: "18+ Hours",
  },
];
const courseLevel = [
  {
    level: "Beginner",
  },
  {
    level: "Intermediates",
  },
  {
    level: "Advanced",
  },
];
</script>
