<!-- <template>
  <Header />
  <div class="mx-24 mt-10 text-4xl font-bold max-[640px]:text-[26px]">
    My Courses
  </div>
  <div class="border mx-24 my-10 max-[640px]:m-8">
    <div class="border p-4 m-4">
      <div>Completed Courses (0)</div>
      <div>In Progress (2)</div>
    </div>
    <div class="text-2xl max-[640px]:text-xl font-bold mt-10 px-8">
      Continue learning
    </div>
    <NuxtLink to="/courseVideo">
      <div class="flex justify-between border p-4 m-4 max-[820px]:flex-col">
        <div class="flex items-center max-[640px]:flex-col">
          <div class="relative">
            <Icon
              name="material-symbols:play-arrow"
              class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black cursor-pointer text-white text-[24px] rounded-full bg-opacity-60"
            />
            <img
              src="https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg"
              class="w-40 h-24"
            />
          </div>
          <div class="ml-4 max-[640px]:mt-2 max-[820px]:border-l-0">
            <div class="font-light max-[640px]:text-sm">Course | Language</div>
            <div class="text-xl max-[640px]:text-[18px]">
              English for career development
            </div>
            <div class="flex items-center">
              <Progress v-model="progress" class="w-3/5 h-[8px]" />
              <div class="mt-2 ml-4">60%</div>
            </div>
            <div class="font-light text-sm">Course: <Badge>Paid</Badge></div>
          </div>
        </div>
        <div
          class="w-1/2 border-l max-[820px]:border-l-0 max-[820px]:border-t max-[820px]:mt-4 max-[820px]:w-full max-[820px]:pt-4"
        >
          <div class="ml-4 max-[820px]:ml-0">
            <div class="flex justify-between items-center mb-2">
              <div>Next Up</div>
              <div>
                <DropdownMenu>
                  <DropdownMenuTrigger>
                    <Icon
                      name="ph:dots-three-outline-vertical-fill"
                      class="text-xl"
                    />
                  </DropdownMenuTrigger>
                  <DropdownMenuContent>
                    <DropdownMenuItem>Unenroll</DropdownMenuItem>
                    <DropdownMenuSeparator />
                    <DropdownMenuItem>Progress</DropdownMenuItem>
                    <DropdownMenuSeparator />
                    <DropdownMenuItem>Get Certificate</DropdownMenuItem>
                  </DropdownMenuContent>
                </DropdownMenu>
              </div>
            </div>
            <div class="font-semibold">Introduction to Communication</div>
            <div class="font-light text-sm">Chapter 3 | Lesson 2</div>
          </div>
        </div>
      </div>
    </NuxtLink>
    <div class="flex justify-between border p-4 m-4 max-[820px]:flex-col">
      <div class="flex items-center max-[640px]:flex-col">
        <div class="relative">
          <Icon
            name="material-symbols:play-arrow"
            class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black cursor-pointer text-white text-[24px] rounded-full bg-opacity-60"
          />
          <img
            src="https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg"
            class="w-40 h-24"
          />
        </div>
        <div class="ml-4 max-[640px]:mt-2 max-[820px]:border-l-0">
          <div class="font-light max-[640px]:text-sm">Course | Language</div>
          <div class="text-xl max-[640px]:text-[18px]">
            English for career development
          </div>
          <div class="font-light text-sm">Course: <Badge>pending </Badge></div>
        </div>
      </div>
      <div
        class="w-1/2 border-l max-[820px]:border-l-0 max-[820px]:border-t max-[820px]:mt-4 max-[820px]:w-full max-[820px]:pt-4"
      >
        <div class="ml-4 max-[820px]:ml-0">
          <div class="flex justify-between items-center mb-2">
            <div><Payment /></div>
            <div>
              <DropdownMenu>
                <DropdownMenuTrigger>
                  <Icon
                    name="ph:dots-three-outline-vertical-fill"
                    class="text-xl"
                  />
                </DropdownMenuTrigger>
                <DropdownMenuContent>
                  <DropdownMenuItem>Unenroll</DropdownMenuItem>
                </DropdownMenuContent>
              </DropdownMenu>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>

<script setup lang="ts">
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";

import { ref, watchEffect } from "vue";
import { Progress } from "@/components/ui/progress";

const progress = ref(13);

watchEffect((cleanupFn) => {
  const timer = setTimeout(() => (progress.value = 60), 500);
  cleanupFn(() => clearTimeout(timer));
});
</script> -->

<template>
  <Header />
  <div class="py-4 px-8 border-b max-[640px]:hidden">
    <div class="flex">
      <div><Button @click="filterCourses('All')">All Course</Button></div>
      <div class="ml-2">
        <Button @click="filterCourses('In Progress')">In Progress</Button>
      </div>
      <div class="ml-2">
        <Button @click="filterCourses('Not Yet Started')"
          >Not Yet Started</Button
        >
      </div>
      <div class="ml-2">
        <Button @click="filterCourses('Completed')">Completed</Button>
      </div>
    </div>
  </div>
  <div class="flex min-[640px]:hidden">
    <div class="mb-4 text-end">
      <Sheet>
        <SheetTrigger class="py-4 px-8">
          <Button class="px-6 py-4 text-xl font-light">
            <Icon name="material-symbols:filter-alt-off-rounded" class="mr-4" />
            Filter my courses
            <Icon
              name="material-symbols:arrow-drop-down-circle"
              class="ml-4"
            /> </Button
        ></SheetTrigger>
        <SheetContent>
          <SheetHeader>
            <SheetTitle class="text-start border-b font-bold"
              >Filter courses</SheetTitle
            >
            <SheetDescription class="pt-4">
              <div class="flex-col text-start">
                <div class="ml-2 mb-2 border-b pb-2">
                  <Button @click="filterCourses('All')">All Course</Button>
                </div>
                <div class="ml-2 mb-2 border-b pb-2">
                  <Button @click="filterCourses('In Progress')"
                    >In Progress</Button
                  >
                </div>
                <div class="ml-2 mb-2 border-b pb-2">
                  <Button @click="filterCourses('Not Yet Started')"
                    >Not Yet Started</Button
                  >
                </div>
                <div class="ml-2 mb-2 border-b pb-2">
                  <Button @click="filterCourses('Completed')">Completed</Button>
                </div>
              </div>
            </SheetDescription>
          </SheetHeader>
        </SheetContent>
      </Sheet>
    </div>
  </div>
  <div class="py-4 px-8">
    <div class="relative w-full max-w-sm items-center my-4">
      <Input
        id="search"
        type="text"
        placeholder="Search course title"
        class="pl-10"
        v-model="searchQuery"
      />
      <span
        class="absolute start-0 inset-y-0 flex items-center justify-center px-2"
      >
        <Icon name="ic:baseline-search" class="size-6 text-muted-foreground" />
      </span>
    </div>
    <div v-for="items in filteredCourses" :key="items.courseId">
      <NuxtLink to="/courseVideo">
        <div
          class="flex border-b pb-10 pt-5 items-center max-[640px]:flex-col max-[640px]:pb-4"
        >
          <div>
            <img
              :src="items.image"
              class="w-[360px] rounded-xl max-[360px]:w-[300px] max-[640px]:w-[380px]"
            />
          </div>
          <div class="flex mt-2">
            <div
              class="ml-4 max-[640px]:ml-0 max-[640px]:mt-2 max-[640px]:text-sm"
            >
              <div class="font-bold">{{ items.title }}</div>
              <div
                class="max-w-[600px] max-[640px]:max-w-full text-start line-clamp-2 text-sm"
              >
                {{ items.description }}
              </div>
              <div class="font-light">
                <span class="text-sm mr-2 font-light">Course by</span
                >{{ items.lecturer }}
              </div>
              <div>
                <Badge> {{ items.status }}</Badge>
              </div>
              <div class="mt-2">
                <div>
                  <div class="">
                    <Progress v-model="progress" class="h-[10px]" />
                    <div class="text-[12px]">24/32 Lessons</div>
                  </div>
                </div>
                <div class="mt-2">
                  <Progress v-model="pointprogress" class="h-[10px]" />
                  <div class="text-[12px]">50/100 point</div>
                </div>
              </div>
            </div>
            <div>
              <DropdownMenu>
                <DropdownMenuTrigger>
                  <Icon
                    name="ph:dots-three-outline-vertical-fill"
                    class="text-xl"
                  />
                </DropdownMenuTrigger>
                <DropdownMenuContent>
                  <DropdownMenuItem>Unenroll</DropdownMenuItem>
                  <DropdownMenuSeparator />
                  <DropdownMenuItem>Get Certificate</DropdownMenuItem>
                </DropdownMenuContent>
              </DropdownMenu>
            </div>
          </div>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
import { Progress } from "@/components/ui/progress";

const progress = ref(0);
const pointprogress = ref(0);

const courses = ref([
  {
    courseId: "c001",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Introduction to Vue.js",
    lecturer: "John Doe",
    description:
      "This course serves as a comprehensive introduction to the Vue.js framework, covering its foundational concepts and practical applications. Ideal for beginners, the curriculum encompasses 12 lessons, providing a solid understanding of Vue.js for web development.",
    level: "beginner",
    duration: "4",
    lessons: 12,
    badge: "New",
    status: "In Progress",
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
    status: "Not Yet Started",
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
    status: "In Progress",
  },
  {
    courseId: "c004",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Advanced JavaScript Programming",
    lecturer: "Jane Smith",
    description:
      "A comprehensive course covering advanced JavaScript topics such as closures, asynchronous programming, and functional programming concepts.",
    level: "advanced",
    duration: "8",
    lessons: 24,
    badge: "Bestseller",
    status: "In Progress",
  },
  {
    courseId: "c005",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Strategic Management",
    lecturer: "Michael Johnson",
    description:
      "An advanced course focusing on strategic management principles and techniques essential for business leaders and executives.",
    level: "advanced",
    duration: "10",
    lessons: 30,
    badge: "Bestseller",
    status: "Completed",
  },
  {
    courseId: "c006",
    category: "Design",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Advanced Typography",
    lecturer: "Sophia Lee",
    description:
      "Dive deep into the art of typography with this advanced-level course covering advanced typographic principles and techniques.",
    level: "advanced",
    duration: "6",
    lessons: 18,
    badge: "Bestseller",
    status: "In Progress",
  },
  {
    courseId: "c007",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Machine Learning Fundamentals",
    lecturer: "Andrew Ng",
    description:
      "A beginner-friendly course introducing the foundational concepts of machine learning, including supervised and unsupervised learning algorithms.",
    level: "beginner",
    duration: "6",
    lessons: 18,
    badge: "New",
    status: "In Progress",
  },
  {
    courseId: "c008",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Financial Accounting Basics",
    lecturer: "David Johnson",
    description:
      "A beginner-level course covering the basic principles and techniques of financial accounting essential for understanding financial statements and reports.",
    level: "beginner",
    duration: "4",
    lessons: 12,
    badge: "New",
    status: "Not Yet Started",
  },
  {
    courseId: "c009",
    category: "Design",
    image:
      "https://www.topuniversities.com/sites/default/files/styles/articles_inline/public/embed-carousel/Online%20Learning%20-%20Header%20Image.jpg.webp",
    title: "Introduction to User Experience Design",
    lecturer: "Sarah Williams",
    description:
      "An introductory course exploring the principles and methodologies of user experience (UX) design, including user research and prototyping techniques.",
    level: "beginner",
    duration: "5",
    lessons: 15,
    badge: "New",
    status: "Completed",
  },
]);

const searchQuery = ref("");
const statusFilter = ref("All");

const filteredCourses = computed(() => {
  return courses.value.filter((course) => {
    const statusMatch =
      statusFilter.value === "All" || course.status === statusFilter.value;
    const searchMatch = course.title
      .toLowerCase()
      .includes(searchQuery.value.toLowerCase());
    return statusMatch && searchMatch;
  });
});

const filterCourses = (status: string) => {
  statusFilter.value = status;
};

watchEffect((cleanupFn) => {
  const timer = setTimeout(() => (progress.value = 75), 2000);
  cleanupFn(() => clearTimeout(timer));
});

watchEffect((cleanupFn) => {
  const pointTimer = setTimeout(() => (pointprogress.value = 50), 2000);
  cleanupFn(() => clearTimeout(pointTimer));
});
</script>
