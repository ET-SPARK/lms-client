<template>
  <div
    class="px-4 py-2 w-full flex items-center flex-col justify-center bg-gray-800 lg:p-8"
  >
    <h1 class="text-gray-100">
      <span>What they’re saying</span>
      <br />
      <span></span>
    </h1>
    <span class="text-gray-100 text-sm max-w-screen-md mt-4 text-center mb-8">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non volutpat
      turpis. Mauris luctus rutrum mi ut rhoncus. Integer in dignissim tortor.
    </span>
    <div class="w-full grid gap-8 grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <TestimonialCard
        v-for="(data, index) in testimonial"
        :key="index"
        :rootClassName="data.rootClassName"
        :picture_src="data.picture_src"
        :quote="data.quote"
        :name="data.author"
        :role="data.occupation"
      ></TestimonialCard>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      testimonial: [
        {
          picture_src:
            "https://images.unsplash.com/photo-1557053910-d9eadeed1c58?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDF8fHdvbWFuJTIwcG9ydHJhaXR8ZW58MHx8fHwxNjI2NDUxOTgy&amp;ixlib=rb-1.2.1&amp;h=1200",
          quote:
            "I've never experienced such a dynamic and supportive learning environment. This platform exceeded my expectations, making complex subjects surprisingly enjoyable to learn.",
          author: "Liam Turner",
          occupation: "IT Professional",
          rootClassName: "rootClassName1",
        },
        {
          picture_src:
            "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHBvcnRyYWl0fGVufDB8fHx8MTYyNjM3ODk3Mg&ixlib=rb-1.2.1&h=1200",

          quote:
            "As an entrepreneur, time is of the essence. The flexibility and quality of courses here allowed me to enhance my skills without compromising my busy schedule. Highly recommend!",
          author: "Emily Chen",
          occupation: "Business Owner",
          rootClassName: "rootClassName2",
        },
        {
          picture_src:
            "https://images.unsplash.com/photo-1531746020798-e6953c6e8e04?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHdvbWFuJTIwcG9ydHJhaXR8ZW58MHx8fHwxNjI2NDUxOTgy&amp;ixlib=rb-1.2.1&amp;h=1200",

          quote:
            "The community aspect is phenomenal. It's not just about learning; it's about connecting with like-minded individuals. I've gained not only knowledge but valuable connections for a lifetime.",
          author: "Alexandra Rodriguez",
          occupation: "Enthusiast",
          rootClassName: "rootClassName3",
        },
      ],
    };
  },
};
</script>
