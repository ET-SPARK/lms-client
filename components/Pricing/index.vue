<template>
  <div
    class="bg-gray-100 w-full flex flex-col py-8 px-4 item-start lg:flex-row lg:p-12"
  >
    <div class="flex flex-col items-start flex-1 mb-4 lg:pr-8">
      <h1 class="text-xl text-left mb-8 font-semibold">Pricing Plans</h1>
      <span class="text-gray-500">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. In lorem lorem,
        malesuada in metus vitae, scelerisque accumsan ipsum.
      </span>
    </div>
    <div
      class="w-auto flex items-center flex-col sm:flex-row sm:justify-between"
    >
      <PricingCard
        v-for="(data, index) in pricing"
        :key="index"
        :rootClassName="data.rootClassName"
        :text="data.planType"
        :text1="data.planPrice"
        :text2="data.PlanDesc"
      ></PricingCard>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pricing: [
        {
          rootClassName: "rootClassName1",
          planType: "Basic",
          planPrice: "Free",
          PlanDesc: [
            {
              title: "Access to a limited selection of courses. ",
            },
            {
              title: "Explore fundamental concepts and skills.",
            },
            {
              title: "Community access for discussions. ",
            },
            {
              title: "",
            },
          ],
        },
        {
          rootClassName: "rootClassName1",
          planType: "Premium",
          planPrice: "500",
          PlanDesc: [
            {
              title: "Full access to all courses.",
            },
            {
              title: "Exclusive content and advanced topics.",
            },
            {
              title: "Instructor Q&A sessions.",
            },
            {
              title: "Achievements and certificates.",
            },
          ],
        },
        {
          rootClassName: "rootClassName1",
          planType: "Business",
          planPrice: "Custom",
          PlanDesc: [
            {
              title: "Tailored solutions for corporate training. ",
            },
            {
              title: "Employee progress tracking and analytics.",
            },
            {
              title: "Dedicated support and customization options. ",
            },
            {
              title: "",
            },
          ],
        },
      ],
    };
  },
};
</script>
