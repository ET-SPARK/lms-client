<template>
  <div class="home-testimonial">
    <div class="home-container08">
      <h1 class="home-text16">
        <span>What they’re saying</span>
        <br />
        <span></span>
      </h1>
      <span class="home-text19">
        <span>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non
          volutpat turpis. Mauris luctus rutrum mi ut rhoncus. Integer in
          dignissim tortor.
        </span>
      </span>
      <div class="home-container09">
        <TestimonialCard
          picture_src="https://images.unsplash.com/photo-1557053910-d9eadeed1c58?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDF8fHdvbWFuJTIwcG9ydHJhaXR8ZW58MHx8fHwxNjI2NDUxOTgy&amp;ixlib=rb-1.2.1&amp;h=1200"
          rootClassName="rootClassName2"
        ></TestimonialCard>
        <TestimonialCard rootClassName="rootClassName"></TestimonialCard>
        <TestimonialCard
          picture_src="https://images.unsplash.com/photo-1531746020798-e6953c6e8e04?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fHdvbWFuJTIwcG9ydHJhaXR8ZW58MHx8fHwxNjI2NDUxOTgy&amp;ixlib=rb-1.2.1&amp;h=1200"
          rootClassName="rootClassName1"
        ></TestimonialCard>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home-testimonial {
  @apply w-full flex justify-center bg-gray-800; /* Replace background color with an appropriate value */
}

.home-container08 {
  @apply w-full flex p-6 lg:p-8 max-w-screen-xl items-center flex-col justify-center;
}

.home-text16 {
  @apply text-gray-100;
}

.home-text19 {
  @apply text-gray-100 text-sm max-w-screen-md mt-4 text-center mb-8;
}

.home-container09 {
  @apply w-full grid gap-8 grid-cols-1 md:grid-cols-2 lg:grid-cols-3;
}

@media (max-width: 991px) {
  .home-text16,
  .home-text19 {
    @apply text-center;
  }
  .home-container09 {
    @apply grid-cols-1;
  }
}

@media (max-width: 767px) {
  .home-container08 {
    @apply pl-4 pr-4;
  }
}

@media (max-width: 479px) {
  .home-container08 {
    @apply pt-4 pl-2 pr-2 pb-4;
  }
}
</style>
