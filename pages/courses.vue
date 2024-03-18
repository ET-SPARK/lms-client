<template>
  <Header />
  <div class="flex p-4 max-[820px]:flex-col">
    <div class="w-[400px] max-[820px]:hidden">
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

    <div class="flex min-[1024px]:hidden">
      <div class="mb-4 text-end">
        <Sheet>
          <SheetTrigger>
            <Button class="px-6 py-4 text-xl font-light">
              <Icon
                name="material-symbols:filter-alt-off-rounded"
                class="mr-4"
              />
              Filter
              <Icon
                name="material-symbols:arrow-drop-down-circle"
                class="ml-4"
              /> </Button
          ></SheetTrigger>
          <SheetContent>
            <SheetHeader>
              <SheetTitle>"" results</SheetTitle>
              <SheetDescription>
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
                <div class="mt-4 text-center">
                  <Button class="px-6 py-4 text-xl font-light">
                    <Icon
                      name="material-symbols:filter-alt-off-rounded"
                      class="mr-4"
                    />
                    Filter
                  </Button>
                </div>
              </SheetDescription>
            </SheetHeader>
          </SheetContent>
        </Sheet>
      </div>
    </div>
    <div class="w-full ml-[100px] max-[820px]:ml-0">
      <div class="font-semibold text-end text-md">"" results</div>
      <div v-for="items in course" :key="items.courseId">
        <NuxtLink to="/courseDetail">
          <div class="flex border-b pb-10 pt-5">
            <div>
              <img
                :src="items.image"
                class="w-[300px] h-[150px] rounded-2xl max-[640px]:w-[160px] max-[640px]:h-[100px]"
              />
            </div>
            <div class="ml-4 max-[640px]:text-sm">
              <div class="font-bold">{{ items.title }}</div>
              <div
                class="max-w-[600px] max-[640px]:max-w-[200px] text-start line-clamp-2 text-sm"
              >
                {{ items.description }}
              </div>
              <div class="font-light">{{ items.lecturer }}</div>
              <div class="font-light text-sm">
                <Icon name="ph:dot-duotone" class="" />{{ items.duration }}
                total hours
                <Icon name="ph:dot-duotone" class="" />{{ items.lessons }}
                lectures
                <Icon name="ph:dot-duotone" class="" />
                {{ items.level }}
              </div>
              <div>
                <Badge> {{ items.badge }}</Badge>
              </div>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
  <Footer />
</template>

<script setup lang="ts">
import { Badge } from "@/components/ui/badge";
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet";
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
    description:
      "This course serves as a comprehensive introduction to the Vue.js framework, covering its foundational concepts and practical applications. Ideal for beginners, the curriculum encompasses 12 lessons, providing a solid understanding of Vue.js for web ",
    level: "beginner",
    duration: "4",
    lessons: 12,
    badge: "New",
  },
  {
    courseId: "c002",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Business Analytics",
    lecturer: "Alice Johnson",
    description:
      "Delve into the dynamic realm of business analytics with Alice Johnson in this intermediate-level course. Spanning 15 lessons over 5 weeks, participants will explore analytical tools and methodologies essential for making informed business decisions.",
    level: "intermediate",
    duration: "5",
    lessons: 15,
    badge: "Popular",
  },
  {
    courseId: "c003",
    category: "Design",
    image:
      "https://www.topuniversities.com/sites/default/files/styles/articles_inline/public/embed-carousel/Online%20Learning%20-%20Header%20Image.jpg.webp",
    title: "Graphic Design Fundamentals",
    lecturer: "Eva Martinez",
    description:
      "Elevate your graphic design skills with Eva Martinez's advanced-level course. Over a span of 6 weeks and 20 lessons, participants will master the fundamental principles of graphic design, paving the way for creative excellence.",
    level: "advanced",
    duration: "6",
    lessons: 20,
    badge: "Bestseller",
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
