<template>
  <div
    class="py-2 px-4 flex sm:p-8 max-w-screen-xl shadow-md items-center flex-col justify-between border"
    v-bind:class="rootClassName"
  >
    <svg viewBox="0 0 950.8571428571428 1024" class="mb-2 w-8 sm:mb-4">
      <path
        d="M438.857 182.857v402.286c0 161.143-131.429 292.571-292.571 292.571h-36.571c-20 0-36.571-16.571-36.571-36.571v-73.143c0-20 16.571-36.571 36.571-36.571h36.571c80.571 0 146.286-65.714 146.286-146.286v-18.286c0-30.286-24.571-54.857-54.857-54.857h-128c-60.571 0-109.714-49.143-109.714-109.714v-219.429c0-60.571 49.143-109.714 109.714-109.714h219.429c60.571 0 109.714 49.143 109.714 109.714zM950.857 182.857v402.286c0 161.143-131.429 292.571-292.571 292.571h-36.571c-20 0-36.571-16.571-36.571-36.571v-73.143c0-20 16.571-36.571 36.571-36.571h36.571c80.571 0 146.286-65.714 146.286-146.286v-18.286c0-30.286-24.571-54.857-54.857-54.857h-128c-60.571 0-109.714-49.143-109.714-109.714v-219.429c0-60.571 49.143-109.714 109.714-109.714h219.429c60.571 0 109.714 49.143 109.714 109.714z"
      ></path>
    </svg>
    <div class="flex items-center flex-col justify-between sm:px-6">
      <span class="mb-4 text-base text-center sm:mb-6">{{ quote }}</span>
      <span class="mb-2 text-lg font-light">{{ name }}</span>
      <span class="mb-4 font-semibold uppercase md:self-center">{{
        role
      }}</span>
      <img
        :alt="picture_alt"
        :src="picture_src"
        class="testimonial-card-image w-12 h-12 object-cover rounded-full"
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
