<template>
  <HeaderGuest />
  <div class="flex p-4 max-[820px]:flex-col">
    <div class="w-[400px] max-[820px]:hidden">
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
                  v-for="category in categories"
                  :key="category"
                >
                  <label>
                    <input
                      type="checkbox"
                      :value="category"
                      v-model="selectedCategories"
                    />
                    {{ category }}
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
                  v-for="level in levels"
                  :key="level"
                >
                  <label>
                    <input
                      type="checkbox"
                      :value="level"
                      v-model="selectedLevels"
                    />
                    {{ level }}
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
              <SheetTitle> {{ filteredCourses.length }} results</SheetTitle>
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
                            v-for="category in categories"
                            :key="category"
                          >
                            <label>
                              <input
                                type="checkbox"
                                :value="category"
                                v-model="selectedCategories"
                              />
                              {{ category }}
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
                            v-for="level in levels"
                            :key="level"
                          >
                            <label>
                              <input
                                type="checkbox"
                                :value="level"
                                v-model="selectedLevels"
                              />
                              {{ level }}
                            </label>
                          </div>
                        </AccordionContent>
                      </AccordionItem>
                    </Accordion>
                  </div>
                </div>
              </SheetDescription>
            </SheetHeader>
          </SheetContent>
        </Sheet>
      </div>
    </div>
    <div class="w-full ml-[100px] max-[820px]:ml-0">
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
          <Icon
            name="ic:baseline-search"
            class="size-6 text-muted-foreground"
          />
        </span>
      </div>
      <div class="font-semibold text-end text-md">
        {{ filteredCourses.length }} results
      </div>
      <div v-for="items in filteredCourses" :key="items.courseId">
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
import { ref, computed } from "vue";
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

// Sample data
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
  },
  {
    courseId: "c010",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Data Structures and Algorithms",
    lecturer: "Mark Brown",
    description:
      "A comprehensive course covering essential data structures and algorithms concepts, including arrays, linked lists, sorting algorithms, and search algorithms.",
    level: "intermediate",
    duration: "8",
    lessons: 24,
    badge: "Popular",
  },
  {
    courseId: "c011",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Marketing Strategies",
    lecturer: "Emily Adams",
    description:
      "An intermediate-level course focusing on advanced marketing strategies, including digital marketing, social media marketing, and content marketing techniques.",
    level: "intermediate",
    duration: "6",
    lessons: 18,
    badge: "Popular",
  },
  {
    courseId: "c012",
    category: "Design",
    image:
      "https://www.topuniversities.com/sites/default/files/styles/articles_inline/public/embed-carousel/Online%20Learning%20-%20Header%20Image.jpg.webp",
    title: "Advanced Web Design",
    lecturer: "Chris Wilson",
    description:
      "An intermediate-level course covering advanced web design techniques, including responsive design, CSS frameworks, and front-end optimization strategies.",
    level: "intermediate",
    duration: "7",
    lessons: 21,
    badge: "Popular",
  },
  {
    courseId: "c013",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Full-Stack Web Development",
    lecturer: "Rachel Miller",
    description:
      "An advanced-level course covering full-stack web development concepts, including front-end frameworks, back-end development, and database management.",
    level: "advanced",
    duration: "10",
    lessons: 30,
    badge: "Bestseller",
  },
  {
    courseId: "c014",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Leadership and Management",
    lecturer: "Alex Clark",
    description:
      "An advanced-level course focusing on leadership and management principles, including strategic leadership, team management, and organizational behavior.",
    level: "advanced",
    duration: "8",
    lessons: 24,
    badge: "Bestseller",
  },
  {
    courseId: "c015",
    category: "Design",
    image:
      "https://www.topuniversities.com/sites/default/files/styles/articles_inline/public/embed-carousel/Online%20Learning%20-%20Header%20Image.jpg.webp",
    title: "Advanced Motion Graphics",
    lecturer: "Daniel Roberts",
    description:
      "An advanced-level course exploring advanced motion graphics techniques, including animation principles, visual effects, and 3D animation software.",
    level: "advanced",
    duration: "9",
    lessons: 27,
    badge: "Bestseller",
  },
  {
    courseId: "c016",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Cybersecurity Fundamentals",
    lecturer: "Sarah Johnson",
    description:
      "A beginner-friendly course introducing the fundamental concepts of cybersecurity, including network security, encryption techniques, and risk management.",
    level: "beginner",
    duration: "5",
    lessons: 15,
    badge: "New",
  },
  {
    courseId: "c017",
    category: "Business",
    image:
      "https://info.ehl.edu/hubfs/Blog-EHL-Insights/Blog-Header-EHL-Insights/advantage%20online%20learning.jpeg",
    title: "Strategic Planning",
    lecturer: "Jessica Brown",
    description:
      "An intermediate-level course focusing on strategic planning processes and frameworks, including SWOT analysis, goal setting, and action planning.",
    level: "intermediate",
    duration: "7",
    lessons: 21,
    badge: "Popular",
  },
  {
    courseId: "c018",
    category: "Design",
    image:
      "https://www.topuniversities.com/sites/default/files/styles/articles_inline/public/embed-carousel/Online%20Learning%20-%20Header%20Image.jpg.webp",
    title: "Advanced Illustration Techniques",
    lecturer: "Michael Lee",
    description:
      "An intermediate-level course exploring advanced illustration techniques, including digital illustration software, character design, and illustration styles.",
    level: "intermediate",
    duration: "6",
    lessons: 18,
    badge: "Popular",
  },
  {
    courseId: "c019",
    category: "IT",
    image:
      "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
    title: "Cloud Computing Essentials",
    lecturer: "Emily Wilson",
    description:
      "An advanced-level course covering cloud computing essentials, including cloud architecture, deployment models, and cloud security.",
    level: "advanced",
    duration: "8",
    lessons: 24,
    badge: "Bestseller",
  },
]);

// Get unique categories from courses
const categories = computed(() => [
  ...new Set(courses.value.map((course) => course.category)),
]);

// Get unique levels from courses
const levels = computed(() => [
  ...new Set(courses.value.map((course) => course.level)),
]);

// Selected categories for filtering
const selectedCategories = ref([]);

// Selected levels for filtering
const selectedLevels = ref([]);

// Search query
const searchQuery = ref("");

// Function to apply filter
const applyFilter = () => {
  // Perform filtering
  let filtered = courses.value;

  // Filter by selected categories
  if (selectedCategories.value.length > 0) {
    filtered = filtered.filter((course) =>
      selectedCategories.value.includes(course.category)
    );
  }

  // Filter by selected levels
  if (selectedLevels.value.length > 0) {
    filtered = filtered.filter((course) =>
      selectedLevels.value.includes(course.level)
    );
  }

  // Filter by search query
  if (searchQuery.value.trim() !== "") {
    const search = searchQuery.value.trim().toLowerCase();
    filtered = filtered.filter(
      (course) =>
        course.title.toLowerCase().includes(search) ||
        course.description.toLowerCase().includes(search) ||
        course.lecturer.toLowerCase().includes(search)
    );
  }

  return filtered;
};

// Computed property for filtered courses
const filteredCourses = computed(() => applyFilter());
</script>
