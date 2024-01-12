<template>
  <div class="grid grid-cols-2 gap-5 justify-between mt-4 mb-4 text-[12px]">
    <div v-for="course in courseNavList" :key="course.icon">
      <NuxtLink
        to="/"
        class="cursor-pointer hover:text-blue-500 flex items-center"
      >
        <div class="bg-blue-500 p-1 mr-2 rounded-md">
          <Icon :name="course.icon" class="text-white text-xl" />
        </div>

        {{ course.name }}
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      courseNavList: [
        {
          icon: "streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting",
          name: "Accounting & Finance",
        },
        {
          icon: "ep:brush",
          name: "Art & Crafts",
        },
        {
          icon: "mdi:brush-off",
          name: "Beauty & Makeup",
        },
        {
          icon: "material-symbols:ink-pen-sharp",
          name: "Creatives & Design",
        },
        {
          icon: "ic:round-fastfood",
          name: "Food & Beverage",
        },
        {
          icon: "material-symbols:ecg-heart-outline",
          name: "Health & Fitness",
        },
        {
          icon: "streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit",
          name: "Business & Marketing",
        },
        {
          icon: "ph:code-bold",
          name: "IT & Development",
        },
        {
          icon: "lucide:languages",
          name: "Language & Literature",
        },
        {
          icon: "guidance:office",
          name: "Office productivity",
        },
        {
          icon: "guidance:meeting-point",
          name: "Personal development",
        },
        {
          icon: "material-symbols:camera",
          name: "Photography & Videography",
        },
      ],
    };
  },
};
</script>
