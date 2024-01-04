<template>
  <div class="testimonial-card-testimonial-card" v-bind:class="rootClassName">
    <svg viewBox="0 0 950.8571428571428 1024" class="testimonial-card-icon">
      <path
        d="M438.857 182.857v402.286c0 161.143-131.429 292.571-292.571 292.571h-36.571c-20 0-36.571-16.571-36.571-36.571v-73.143c0-20 16.571-36.571 36.571-36.571h36.571c80.571 0 146.286-65.714 146.286-146.286v-18.286c0-30.286-24.571-54.857-54.857-54.857h-128c-60.571 0-109.714-49.143-109.714-109.714v-219.429c0-60.571 49.143-109.714 109.714-109.714h219.429c60.571 0 109.714 49.143 109.714 109.714zM950.857 182.857v402.286c0 161.143-131.429 292.571-292.571 292.571h-36.571c-20 0-36.571-16.571-36.571-36.571v-73.143c0-20 16.571-36.571 36.571-36.571h36.571c80.571 0 146.286-65.714 146.286-146.286v-18.286c0-30.286-24.571-54.857-54.857-54.857h-128c-60.571 0-109.714-49.143-109.714-109.714v-219.429c0-60.571 49.143-109.714 109.714-109.714h219.429c60.571 0 109.714 49.143 109.714 109.714z"
      ></path>
    </svg>
    <div class="testimonial-card-testimonial">
      <span class="testimonial-card-text">{{ quote }}</span>
      <span class="testimonial-card-text1">{{ name }}</span>
      <span class="testimonial-card-text2">{{ role }}</span>
      <img
        :alt="picture_alt"
        :src="picture_src"
        class="testimonial-card-image"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "TestimonialCard",
  props: {
    picture_src: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&h=1200",
    },
    quote: {
      type: String,
      default:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In lorem lorem, malesuada in metus vitae, scelerisque accumsan ipsum.  Nam pellentesque nulla leo, sagittis vehicula sem commodo nec.",
    },
    picture_alt: {
      type: String,
      default: "profile",
    },
    name: {
      type: String,
      default: "Jane Doe",
    },
    rootClassName: String,
    role: {
      type: String,
      default: "SOFTWARE ENGINEER",
    },
  },
};
</script>

<style scoped>
.testimonial-card-testimonial-card {
  @apply flex p-8 max-w-screen-xl bg-white shadow-md items-center flex-col justify-between;
}

.testimonial-card-icon {
  @apply w-8 mb-4;
}

.testimonial-card-testimonial {
  @apply flex items-center flex-col justify-between;
}

.testimonial-card-text {
  @apply text-gray-500 text-center mb-6;
}

.testimonial-card-text1 {
  @apply text-2xl font-light mb-2;
}

.testimonial-card-text2 {
  @apply text-gray-500 font-semibold mb-4 uppercase;
}

.testimonial-card-image {
  @apply w-12 h-12 object-cover rounded-full;
}

@media (max-width: 991px) {
  .testimonial-card-text2 {
    @apply self-center;
  }
}

@media (max-width: 767px) {
  .testimonial-card-testimonial-card {
    @apply pl-4 pr-4;
  }
}

@media (max-width: 479px) {
  .testimonial-card-testimonial-card {
    @apply pt-4 pl-2 pr-2 pb-4;
  }
  .testimonial-card-icon {
    @apply mb-2;
  }
  .testimonial-card-text {
    @apply mb-4;
  }
  .testimonial-card-text1 {
    @apply mb-2;
  }
  .testimonial-card-text2 {
    @apply mb-4;
  }
}
</style>
