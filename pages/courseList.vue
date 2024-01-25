<template>
  <HeaderGuest />
  <div class="flex justify-between mt-10 mb-10 ml-10">
    <div>
      <div class="border-b font-light text-xl">CATEGORIES</div>
      <div
        class="cursor-pointer text-blue-500 underline text-[14px] text-end mt-2"
        @click="selectCategory(null)"
      >
        View all
      </div>
      <!-- <div class="flex1 mt-5">
        <div class="flex-1 font-light border-b-2">
          <div class="justify-between mt-4 mb-4">
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Accounting & Finance')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Accounting & Finance</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Art & Crafts')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="ep:brush"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Art & Crafts</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Beauty & Makeup')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="mdi:brush-off"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Beauty & Makeup</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Creatives & Design')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="material-symbols:ink-pen-sharp"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Creatives & Design</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Food & Beverage')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="ic:round-fastfood"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Food & Beverage</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Health & Fitness')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="material-symbols:ecg-heart-outline"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Health & Fitness</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Language & Literature')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="lucide:languages"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Language & Literature</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Music & Theater')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="ph:music-notes-fill"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Music & Theater</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Office Productivity')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="guidance:office"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Office productivity</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Personal Development')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="guidance:meeting-point"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Personal development</div>
            </div>
            <div
              class="flex items-center p-4 cursor-pointer"
              @click="selectCategory('Photography & Videography')"
            >
              <div class="bg-blue-500 p-1 mr-2 rounded-md">
                <Icon
                  name="material-symbols:camera"
                  class="cursor-pointer text-white text-2xl"
                />
              </div>
              <div>Photography & Videography</div>
            </div>
          </div>
        </div>
      </div> -->
      <div>
        <NavMobCourseNav class="text-[18px]" />
      </div>
    </div>
    <div class="flex-1 pl-10">
      <div class="border-b font-semibold text-xl">Courses</div>
      <div class="mt-5">
        <div
          v-for="(category, index) in courseList"
          :key="index"
          class="grid grid-cols-3 gap-2"
        >
          <p
            v-if="!selectedCategory || selectedCategory === category.category"
            class="text-xl font-semibold mb-4"
          >
            {{ category.category }}
          </p>

          <div
            v-if="!selectedCategory || selectedCategory === category.category"
            v-for="(course, courseIndex) in category.courses"
            :key="courseIndex"
            class="mt-5 border mr-5 rounded-xl"
          >
            <div>
              <div class="relative">
                <!-- Your Icon component with 'course.iconName' -->
                <Icon
                  name="material-symbols:play-arrow"
                  class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black cursor-pointer text-white text-4xl rounded-full bg-opacity-60"
                />
                <img :src="course.imageSource" class="rounded-t-xl" />
              </div>
              <div class="border-t-2 px-3 h-[100px]">
                <div>
                  <p class="text-xl">{{ course.title }}</p>
                </div>
                <div class="text-sm">A course by: {{ course.author }}</div>
                <div>
                  <p class="text-sm">{{ course.description }}</p>
                </div>
              </div>
              <div
                class="flex justify-between border-t-2 px-3 mt-12 items-center"
              >
                <div class="text-center">
                  <div>
                    <!-- Your Icon component with 'course.level' -->
                    <Icon
                      name="carbon:skill-level-basic"
                      class="cursor-pointer mr-1"
                    />Level
                  </div>
                  <div class="font-bold">{{ course.level }}</div>
                </div>
                <div class="text-center">
                  <div>
                    <!-- Your Icon component with 'course.duration' -->
                    <Icon
                      name="mdi:clock-time-eleven"
                      class="cursor-pointer mr-1"
                    />Duration
                  </div>
                  <div class="font-bold">{{ course.duration }}</div>
                </div>
                <div class="text-center">
                  <div>
                    <!-- Your Icon component with 'course.lessons' -->
                    <Icon
                      name="material-symbols:play-lesson"
                      class="cursor-pointer mr-1"
                    />Lessons
                  </div>
                  <div class="font-bold">{{ course.lessons }}</div>
                </div>
              </div>
              <div class="flex justify-center border-t-2 px-3 py-2">
                <NuxtLink to="/course">
                  <Button> Get started </Button></NuxtLink
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <FooterGuest />
</template>

<script>
export default {
  data() {
    return {
      courseList: [
        {
          category: "Accounting & Finance",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Financial Accounting Basics",
              author: "John Smith",
              description: "Learn the fundamentals of financial accounting.",
              level: "Beginner",
              duration: "3:00 h",
              lessons: 25,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Advanced Investment Strategies",
              author: "Emily Johnson",
              description:
                "Explore advanced investment techniques and strategies.",
              level: "Advanced",
              duration: "6:30 h",
              lessons: 40,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Introduction to Financial Management",
              author: "Alice Johnson",
              description: "Learn the basics of financial management.",
              level: "Beginner",
              duration: "2:30 h",
              lessons: 20,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Advanced Corporate Finance",
              author: "Robert Davis",
              description:
                "Delve into advanced concepts of corporate finance and decision-making.",
              level: "Advanced",
              duration: "5:00 h",
              lessons: 35,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Advanced Corporate Finance",
              author: "Robert Davis",
              description:
                "Delve into advanced concepts of corporate finance and decision-making.",
              level: "Advanced",
              duration: "5:00 h",
              lessons: 35,
            },

            // Add more courses for Accounting & Finance as needed
          ],
        },
        {
          category: "Art & Crafts",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Oil Painting Mastery",
              author: "Alicia Turner",
              description:
                "Master the art of oil painting with hands-on techniques.",
              level: "Intermediate",
              duration: "4:30 h",
              lessons: 30,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Sculpture Techniques",
              author: "Michael Davis",
              description:
                "Learn various sculpture techniques from basics to advanced.",
              level: "Advanced",
              duration: "8:00 h",
              lessons: 55,
            },
            // Add more courses for Art & Crafts as needed
          ],
        },
        {
          category: "Beauty & Makeup",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Makeup Artistry Basics",
              author: "Sophia Rodriguez",
              description:
                "Discover the basics of makeup artistry and beauty techniques.",
              level: "Beginner",
              duration: "2:30 h",
              lessons: 20,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Advanced Skincare Routines",
              author: "Daniel Lee",
              description:
                "Learn advanced skincare routines and beauty tips for different skin types.",
              level: "Advanced",
              duration: "5:00 h",
              lessons: 35,
            },
            // Add more courses for Beauty & Makeup as needed
          ],
        },
        {
          category: "Creatives & Design",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Graphic Design Fundamentals",
              author: "Eva Thompson",
              description:
                "Master the basics of graphic design and visual communication.",
              level: "Intermediate",
              duration: "4:00 h",
              lessons: 30,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "UI/UX Design Principles",
              author: "Christopher White",
              description:
                "Explore the principles of user interface and user experience design.",
              level: "Advanced",
              duration: "6:30 h",
              lessons: 45,
            },
            // Add more courses for Creatives & Design as needed
          ],
        },
        {
          category: "Food & Beverage",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Culinary Arts: From Basics to Gourmet",
              author: "Isabella Martin",
              description:
                "Learn culinary arts from the basics to gourmet cooking techniques.",
              level: "Intermediate",
              duration: "5:00 h",
              lessons: 40,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Beverage Mixology Masterclass",
              author: "David Johnson",
              description:
                "Master the art of creating delightful beverages with mixology techniques.",
              level: "Advanced",
              duration: "7:00 h",
              lessons: 50,
            },
            // Add more courses for Food & Beverage as needed
          ],
        },
        {
          category: "Health & Fitness",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Fitness for Beginners",
              author: "Jessica Miller",
              description:
                "Start your fitness journey with basic exercises and healthy habits.",
              level: "Beginner",
              duration: "3:00 h",
              lessons: 25,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Advanced Yoga and Meditation",
              author: "Ryan Carter",
              description:
                "Explore advanced yoga poses and meditation techniques for mental and physical well-being.",
              level: "Advanced",
              duration: "5:30 h",
              lessons: 35,
            },
            // Add more courses for Health & Fitness as needed
          ],
        },
        {
          category: "Language & Literature",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Spanish Language Mastery",
              author: "Isabella Hernandez",
              description:
                "Master the Spanish language with comprehensive lessons and practice exercises.",
              level: "Intermediate",
              duration: "4:30 h",
              lessons: 30,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Classic Literature Appreciation",
              author: "Andrew Thompson",
              description:
                "Explore classic literature from different genres and time periods.",
              level: "Advanced",
              duration: "6:00 h",
              lessons: 40,
            },
            // Add more courses for Language & Literature as needed
          ],
        },
        {
          category: "Music & Theater",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Introduction to Music Theory",
              author: "Sophie Davis",
              description:
                "Learn the fundamentals of music theory and notation.",
              level: "Beginner",
              duration: "3:30 h",
              lessons: 28,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Acting Techniques for Stage and Screen",
              author: "Michael Johnson",
              description:
                "Explore acting techniques for both stage and screen performances.",
              level: "Intermediate",
              duration: "5:30 h",
              lessons: 45,
            },
            // Add more courses for Music & Theater as needed
          ],
        },
        {
          category: "Office Productivity",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Mastering Microsoft Office",
              author: "Emily White",
              description:
                "Become proficient in using Microsoft Office applications for enhanced productivity.",
              level: "Intermediate",
              duration: "4:00 h",
              lessons: 35,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Effective Time Management",
              author: "David Miller",
              description:
                "Learn time management strategies and techniques for increased efficiency.",
              level: "Advanced",
              duration: "6:30 h",
              lessons: 50,
            },
            // Add more courses for Office Productivity as needed
          ],
        },
        {
          category: "Personal Development",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Goal Setting and Achievement",
              author: "Sophia Anderson",
              description:
                "Set and achieve meaningful personal and professional goals.",
              level: "Intermediate",
              duration: "3:30 h",
              lessons: 30,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Mindfulness and Stress Reduction",
              author: "Daniel Smith",
              description:
                "Practice mindfulness techniques for stress reduction and improved well-being.",
              level: "Advanced",
              duration: "5:30 h",
              lessons: 40,
            },
            // Add more courses for Personal Development as needed
          ],
        },
        {
          category: "Photography & Videography",
          courses: [
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Digital Photography Basics",
              author: "Emma Davis",
              description:
                "Learn the basics of digital photography, camera settings, and composition.",
              level: "Beginner",
              duration: "3:00 h",
              lessons: 25,
            },
            {
              imageSource:
                "https://www.cypherlearning.com/hubfs/Imported_Blog_Media/A-teachers-guide-to-becoming-an-online-course-creator.jpg",
              title: "Cinematic Videography Techniques",
              author: "Alexandra Johnson",
              description:
                "Explore cinematic videography techniques for creating compelling videos.",
              level: "Intermediate",
              duration: "5:00 h",
              lessons: 35,
            },
            // Add more courses for Photography & Videography as needed
          ],
        },
      ],
      selectedCategory: null,
    };
  },
  methods: {
    selectCategory(category) {
      this.selectedCategory = category;
    },
  },
};
</script>
