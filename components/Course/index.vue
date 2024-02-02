<template>
  <div class="my-10 border-b pb-10">
    <p
      class="text-[32px] text-center font-bold max-[768px]:text-[24px] max-[640px]:text-[20px] mt-10 mb-10"
    >
      Grow Your Skill Set
    </p>

    <CoursePopular />
    <CourseNew />

    <NuxtLink to="/courses">
      <Button class="mt-20 flex justify-end ml-16 max-[640px]:text-sm">
        View all
      </Button>
    </NuxtLink>
  </div>
</template>
