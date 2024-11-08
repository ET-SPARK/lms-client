<template>
  <div
    class="w-full flex flex-col p-4 max-w-screen-xl items-start justify-center"
    v-bind:class="rootClassName"
  >
    <Icon :name="icon" class="cursor-pointer text-2xl" />
    <h2 class="font-semibold mb-4">{{ title }}</h2>
    <span class="text-gray-700">{{ description }}</span>
  </div>
</template>

<script>
export default {
  name: "FeatureCard",
  props: {
    description: {
      type: String,
      default:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In lorem lorem, malesuada in metus vitae, scelerisque accumsan ipsum.",
    },
    rootClassName: String,
    icon: String,
    title: {
      type: String,
      default: "Lorem ipsum",
    },
  },
};
</script>
