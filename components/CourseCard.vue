<template>
  <div class="course-card-feature-card" v-bind:class="rootClassName">
    <img
      :alt="image_alt"
      :src="image_src"
      image_src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&amp;ixlib=rb-1.2.1&amp;h=1000"
      class="course-card-image"
    />
    <div class="course-card-container">
      <div class="course-card-container1">
        <span class="course-card-text">{{ text1 }}</span>
        <span class="course-card-text1">{{ text2 }}</span>
      </div>
      <h1 class="course-card-text2">{{ heading }}</h1>
      <span class="course-card-text3">{{ text }}</span>
      <div class="course-card-container2">
        <div class="course-card-profile">
          <img :alt="image_alt1" :src="image_src1" class="course-card-image1" />
          <span class="course-card-text4">{{ text4 }}</span>
        </div>
        <span class="course-card-text5">{{ text3 }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CourseCard",
  props: {
    image_src: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&w=300",
    },
    text4: {
      type: String,
      default: "Jane Doe",
    },
    rootClassName: String,
    title: {
      type: String,
      default: "Lorem ipsum",
    },
    text1: {
      type: String,
      default: "ENTERPRISE",
    },
    image_alt: {
      type: String,
      default: "image",
    },
    image_alt1: {
      type: String,
      default: "profile",
    },
    image_src1: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&w=200",
    },
    text2: {
      type: String,
      default: "3 days ago",
    },
    heading: {
      type: String,
      default: "Lorem ipsum dolor sit amet",
    },
    text3: {
      type: String,
      default: "Read More ->",
    },
    text: {
      type: String,
      default:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non volutpat turpis. Mauris luctus rutrum mi ut rhoncus. Integer in dignissim tortor. Lorem ipsum dolor sit amet, consectetur adipiscing ...",
    },
    action: {
      type: String,
      default: "SEE MORE",
    },
    description: {
      type: String,
      default: "Lorem ipsum dolor sit amet, consectetur adipiscing.",
    },
  },
};
</script>

<style scoped>
.course-card-feature-card {
  @apply w-full flex flex-col p-4 items-center;
}
.course-card-image {
  @apply w-full h-52 object-cover flex-shrink-0 rounded-3xl;
}
.course-card-container {
  @apply flex flex-col p-2  items-start  justify-between;
}
.course-card-container1 {
  @apply w-full flex items-start mb-2  flex-row justify-between;
}
.course-card-text {
  @apply text-gray-500 text-xs font-semibold uppercase;
}
.course-card-text1 {
  @apply text-gray-500 text-xs font-light;
}
.course-card-text2 {
  @apply text-lg mb-4;
}

.course-card-text3 {
  @apply text-gray-500 text-xs mb-4;
}

.course-card-container2 {
  @apply w-full flex items-center flex-row justify-between;
}

.course-card-profile {
  @apply flex items-center;
}

.course-card-image1 {
  @apply w-6 h-6 object-cover rounded-full;
}

.course-card-text4 {
  @apply text-xs font-semibold ml-2;
}
.course-card-text5 {
  @apply text-gray-700 text-sm font-medium ml-2;
}

@media (max-width: 767px) {
  .course-card-image {
    @apply w-full;
  }
}
@media (max-width: 479px) {
  .course-card-container2 {
    @apply pl-0 pr-0;
  }
  .course-card-text5 {
    @apply w-auto;
  }
}
</style>
