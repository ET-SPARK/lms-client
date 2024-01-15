<template>
  <div
    class="w-full flex flex-col p-4 items-center"
    v-bind:class="rootClassName"
  >
    <img
      :alt="image_alt"
      :src="image_src"
      image_src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&amp;ixlib=rb-1.2.1&amp;h=1000"
      class="w-full h-52 object-cover flex-shrink-0 rounded-3xl"
    />
    <div class="flex flex-col p-2 items-start justify-between">
      <div class="w-fit mb-2 border-2 px-2 rounded-2xl">
        <span class="text-gray-500 text-xs font-semibold uppercase">{{
          type
        }}</span>
      </div>
      <h1 class="text-lg mb-4">{{ heading }}</h1>
      <span class="text-gray-500 text-xs mb-4">{{ description }}</span>
      <div class="w-full flex items-center flex-row justify-between">
        <div class="flex items-center">
          <img
            :alt="instructor_image_alt1"
            :src="instructor_image_src1"
            class="w-6 h-6 object-cover rounded-full"
          />
          <span class="text-xs font-semibold ml-2">{{ instructor }}</span>
        </div>
        <Button class="text-white rounded-lg text-xs font-medium">{{
          action
        }}</Button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CourseCard",
  props: {
    instructor: {
      type: String,
      default: "Jane Doe",
    },
    rootClassName: String,

    type: {
      type: String,
      default: "ENTERPRISE",
    },
    image_src: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&w=300",
    },
    image_alt: {
      type: String,
      default: "image",
    },
    instructor_image_alt1: {
      type: String,
      default: "profile",
    },
    instructor_image_src1: {
      type: String,
      default:
        "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&w=200",
    },

    heading: {
      type: String,
      default: "Lorem ipsum dolor sit amet",
    },
    action: {
      type: String,
      default: "Read More",
    },
    description: {
      type: String,
      default:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non volutpat turpis. Mauris luctus rutrum mi ut rhoncus. Integer in dignissim tortor. Lorem ipsum dolor sit amet, consectetur adipiscing ...",
    },
  },
};
</script>
