<template>
  <div
    class="w-full max-w-72 h-72 flex-1 flex flex-col mx-2 px-4 py-8 mb-2 items-center shadow-md rounded-md justify-between border"
    v-bind:class="rootClassName"
  >
    <h2 class="text-xl font-bold text-center mb-4">
      {{ text }}
    </h2>
    <h3 class="1 m-2 text-4xl font-light">
      <span class="text-xl" v-if="text1 !== 'Custom' && text1 !== 'Free'">
        $
      </span>
      {{ text1 }}
      <span class="text-xl" v-if="text1 !== 'Custom' && text1 !== 'Free'">
        Br/month
      </span>
    </h3>
    <span
      class="text-xs text-justify font-normal"
      v-for="(data, index) in text2"
      :key="index"
    >
      {{ data.title }}
    </span>

    <Button class="text-xs py-1 px-2 border-0">{{ button }}</Button>
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
      default: "0",
    },
    text2: {
      type: Object,
      default: [
        {
          title: " * Lorem ipsum dolor sit amet",
        },
        {
          title: " * Lorem ipsum dolor sit amet",
        },
        {
          title: " * Lorem ipsum dolor sit amet",
        },
        {
          title: " * Lorem ipsum dolor sit amet",
        },
      ],
    },
    button: {
      type: String,
      default: "Learn More",
    },
    rootClassName: String,
  },
};
</script>
