<template>
  <div class="pricing-card-container" v-bind:class="rootClassName">
    <span class="pricing-card-text">{{ text }}</span>
    <span class="pricing-card-text01">{{ text1 }}</span>
    <span class="pricing-card-text02">
      <span class="pricing-card-text03">10</span>
      <span>Projects</span>
    </span>
    <span class="pricing-card-text05">
      <span class="pricing-card-text06">99</span>
      <span>Components</span>
    </span>
    <span class="pricing-card-text08">
      <span class="pricing-card-text09">3</span>
      <span>Collaborators</span>
    </span>
    <span class="pricing-card-text11">
      <span class="pricing-card-text12">Public projects</span>
    </span>
    <button class="pricing-card-button button">{{ button }}</button>
  </div>
</template>

<script>
export default {
  name: "PricingCard",
  props: {
    text: {
      type: String,
      default: "Free",
    },
    text1: {
      type: String,
      default: "$0",
    },
    button: {
      type: String,
      default: "Learn More",
    },
    rootClassName: String,
  },
};
</script>

<style scoped>
.pricing-card-container {
  @apply flex-1 flex h-72 flex-col relative max-w-xs mx-2 shadow-md transition-transform items-center pt-8 pr-4 pl-4 pb-8 bg-white;
}
.pricing-card-container:hover {
  @apply scale-105 rounded-lg bg-gray-700 text-white;
}

.pricing-card-text {
  @apply text-xl font-semibold;
}

.pricing-card-text01 {
  @apply m-2 text-4xl font-light;
}

.pricing-card-text02 {
  @apply mb-2;
}

.pricing-card-text03 {
  @apply font-bold;
}

.pricing-card-text05 {
  @apply mb-2;
}

.pricing-card-text06 {
  @apply font-bold;
}

.pricing-card-text08 {
  @apply mb-2;
}

.pricing-card-text09 {
  @apply font-bold;
}

.pricing-card-text11 {
  @apply mb-2;
}

.pricing-card-text12 {
  @apply font-bold;
}

.pricing-card-button {
  @apply text-white mt-auto pt-2 pl-4 pr-4 pb-2 border-0 bg-black;
}

@media (max-width: 767px) {
  .pricing-card-container {
    @apply w-full  mb-4;
  }
}
</style>
