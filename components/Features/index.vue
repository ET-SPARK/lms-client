<template>
  <div class="w-full flex flex-col py-8 px-4 md:px-8 lg:p-12 mt-20">
    <h1 class="text-xl text-left mb-8 font-semibold md:text-2xl">
      Why Choose Us
    </h1>
    <div class="w-24 h-1 bg-gray-600"></div>
    <div class="w-full flex items-center flex-col justify-between lg:flex-row">
      <div class="grid grid-cols-1 gap-4 mb-3 md:grid-cols-2">
        <FeaturesCard
          v-for="(feature, index) in features"
          :key="index"
          :rootClassName="feature.rootClassName"
          :title="feature.title"
          :description="feature.description"
        ></FeaturesCard>
      </div>
      <img
        alt="image"
        src="https://www.elegantthemes.com/layouts/wp-content/uploads/2017/12/coding-isometric-01.png"
        class="w-full h-auto object-cover self-center rounded-full md:w-1/2 md:ml-16 lg:w-1/2 xl:w-1/3"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          rootClassName: "rootClassName1",
          title: "Diverse Course Catalog",
          description:
            "Choose from a diverse array of courses tailored to your interests",
        },
        {
          rootClassName: "rootClassName2",
          title: "Expert-Guided Learning",
          description:
            "Benefit from the expertise of industry professionals and seasoned educators",
        },

        {
          rootClassName: "rootClassName3",
          title: "Flexible Scheduling",
          description:
            "Learn at your own pace with 24/7 access to course materials",
        },

        {
          rootClassName: "rootClassName4",
          title: "Interactive Learning Experiences",
          description:
            "Immerse yourself in interactive lessons and hands-on projects",
        },
      ],
    };
  },
};
</script>
