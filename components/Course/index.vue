<template>
  <div class="home-features1">
    <h1 class="home-text21">
      <span>Explore our services</span>
      <br />
      <span></span>
    </h1>
    <span class="home-text24">
      <span>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. In lorem lorem,
        malesuada in metus vitae, scelerisque accumsan ipsum. Nam pellentesque
        nulla leo, sagittis vehicula sem commodo nec.​
      </span>
      <span></span>
    </span>
    <div class="home-container10">
      <CourseCard rootClassName="rootClassName3"></CourseCard>
      <CourseCard rootClassName="rootClassName7"></CourseCard>
      <CourseCard rootClassName="rootClassName6"></CourseCard>
      <CourseCard rootClassName="rootClassName5"></CourseCard>
      <CourseCard rootClassName="rootClassName4"></CourseCard>
      <CourseCard rootClassName="rootClassName2"></CourseCard>
      <CourseCard rootClassName="rootClassName1"></CourseCard>
      <CourseCard rootClassName="rootClassName"></CourseCard>
    </div>
  </div>
</template>

<style scoped>
.home-features1 {
  @apply w-full flex p-6  items-center flex-col;
}
.home-text21 {
  @apply text-3xl mb-8 text-center;
}
.home-text24 {
  @apply text-gray-700 w-3/4 text-center text-lg;
}

.home-container10 {
  @apply w-full grid gap-8 self-center grid-cols-4;
}
@media (max-width: 991px) {
  .home-text21 {
    @apply text-center;
  }
  .home-text24 {
    @apply text-center;
  }
  .home-container10 {
    @apply grid-cols-3;
  }
}
@media (max-width: 767px) {
  .home-features1 {
    @apply pl-4 pr-4;
  }
  .home-text21 {
    @apply text-center;
  }
  .home-container10 {
    @apply grid-cols-2;
  }
}

@media (max-width: 479px) {
  .home-features1 {
    @apply pt-4 pl-2 pr-2 pb-4;
  }
  .home-container10 {
    @apply grid-cols-1;
  }
}

@media (max-width: 350px) {
  .home-text21 {
    @apply text-2xl;
  }
  .home-container10 {
    @apply grid-cols-1;
  }
}
</style>
