<template>
  <div>
    <h1>Filterable Courses</h1>
    <div>
      <h3>Filter by Category:</h3>
      <label v-for="category in categories" :key="category">
        <input type="checkbox" :value="category" v-model="selectedCategories" />
        {{ category }}
      </label>
    </div>
    <div>
      <h3>Filter by Level:</h3>
      <label v-for="level in levels" :key="level">
        <input type="checkbox" :value="level" v-model="selectedLevels" />
        {{ level }}
      </label>
    </div>
    <div></div>
    <p v-if="filteredCourses.length === 0">No courses found.</p>
    <p v-else>Number of filtered results: {{ filteredCourses.length }}</p>
    <ul v-if="filteredCourses.length > 0">
      <li v-for="course in filteredCourses" :key="course.courseId">
        <img :src="course.image" alt="Course Image" />
        <h3>{{ course.title }}</h3>
        <p>{{ course.description }}</p>
        <p>Lecturer: {{ course.lecturer }}</p>
        <p>Level: {{ course.level }}</p>
        <p>Duration: {{ course.duration }} weeks</p>
        <p>Lessons: {{ course.lessons }}</p>
        <p>Badge: {{ course.badge }}</p>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

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
