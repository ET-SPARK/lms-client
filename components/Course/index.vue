<template>
  <div class="py-2 px-4 w-full flex items-center flex-col">
    <h1 class="text-xl">Explore our services</h1>
    <span class="text-gray-700 text-md d w-3/4 text-center">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    </span>
    <div
      class="grid-cols-1 w-full grid gap-8 self-center sm:grid-cols-2 lg:grid-cols-3"
    >
      <CourseCard
        v-for="(data, index) in courses"
        :key="index"
        :rootClassName="data.rootClassName"
        :instructor="data.instructor"
        :type="data.category"
        :heading="data.title"
        :description="data.description"
        :action="data.action"
      ></CourseCard>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      courses: [
        {
          rootClassName: "rootClassName1",
          title: "Introduction to Coding",
          category: "Programming",
          instructor: "John Doe",
          duration: "4 weeks",
          level: "Beginner",
          description: "An introductory course to coding for beginners.",
          image: "https://example.com/coding-course-image.jpg",
          action: "Buy Now",
        },
        {
          rootClassName: "rootClassName2",
          title: "Digital Marketing Fundamentals",
          category: "Marketing",
          instructor: "Jane Smith",
          duration: "6 weeks",
          level: "Intermediate",
          description:
            "Learn the basics of digital marketing strategies and techniques.",
          image: "https://example.com/marketing-course-image.jpg",
          action: "Start Course",
        },
        {
          rootClassName: "rootClassName3",
          title: "Artificial Intelligence Essentials",
          category: "Technology",
          instructor: "Dr. Alex Johnson",
          duration: "8 weeks",
          level: "Advanced",
          description:
            "Explore the fundamentals of artificial intelligence and machine learning.",
          image: "https://example.com/ai-course-image.jpg",
          action: "Buy Now",
        },
        {
          rootClassName: "rootClassName4",
          title: "Graphic Design Mastery",
          category: "Design",
          instructor: "Emily Thompson",
          duration: "5 weeks",
          level: "Intermediate",
          description:
            "Master the art of graphic design with hands-on projects and creative exercises.",
          image: "https://example.com/design-course-image.jpg",
          action: "Continue",
        },
        {
          rootClassName: "rootClassName5",
          title: "Business Finance for Entrepreneurs",
          category: "Business",
          instructor: "David Rogers",
          duration: "7 weeks",
          level: "Intermediate",
          description:
            "Gain financial literacy and make informed decisions for your business.",
          image: "https://example.com/business-course-image.jpg",
          action: "Buy Now",
        },
        {
          rootClassName: "rootClassName6",
          title: "Photography Basics",
          category: "Photography",
          instructor: "Sarah Davis",
          duration: "4 weeks",
          level: "Beginner",
          description:
            "Learn the essentials of photography, from composition to editing.",
          image: "https://example.com/photography-course-image.jpg",
          action: "Start Course",
        },
        {
          rootClassName: "rootClassName7",
          title: "Spanish Language Immersion",
          category: "Language",
          instructor: "Carlos Rodriguez",
          duration: "6 weeks",
          level: "Intermediate",
          description:
            "Immerse yourself in the Spanish language and culture with interactive lessons.",
          image: "https://example.com/spanish-course-image.jpg",
          action: "Buy Now",
        },
      ],
    };
  },
};
</script>
