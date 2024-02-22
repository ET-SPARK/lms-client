<template>
  <div class="flex items-center hover:bg-secondary cursor-pointer">
    <div class="p-1 mr-2 rounded-md">
      <Icon :name="icon" class="text-2xl" />
    </div>
    <div>{{ name }}</div>
  </div>
</template>

<script>
export default {
  props: {
    icon: String,
    name: String,
  },
};
</script>
