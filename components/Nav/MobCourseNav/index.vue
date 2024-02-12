<template>
  <div class="mt-4 mb-4 text-[12px] max-[600px]:text-[12px]">
    <div
      v-for="course in courseNavList"
      :key="course.icon"
      class="hover:text-blue-500"
    >
      <NuxtLink
        class="cursor-pointer flex items-center"
        :to="{
          path: '/courses',
          query: { categorie: course.categorie },
        }"
      >
        <div class="p-1 mr-2 rounded-md">
          <Icon :name="course.icon" class="text-xl max-[600px]:text-[12px]" />
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
          categorie: "accounting",
        },
        {
          icon: "ep:brush",
          name: "Art & Crafts",
          categorie: "art",
        },
        {
          icon: "mdi:brush-off",
          name: "Beauty & Makeup",
          categorie: "beauty",
        },
        {
          icon: "material-symbols:ink-pen-sharp",
          name: "Creatives & Design",
          categorie: "creatives",
        },
        {
          icon: "ic:round-fastfood",
          name: "Food & Beverage",
          categorie: "food",
        },
        {
          icon: "material-symbols:ecg-heart-outline",
          name: "Health & Fitness",
          categorie: "health",
        },
        {
          icon: "streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit",
          name: "Business & Marketing",
          categorie: "business",
        },
        {
          icon: "ph:code-bold",
          name: "IT & Development",
          categorie: "it",
        },
        {
          icon: "lucide:languages",
          name: "Language & Literature",
          categorie: "language",
        },
        {
          icon: "guidance:office",
          name: "Office productivity",
          categorie: "office",
        },
        {
          icon: "guidance:meeting-point",
          name: "Personal development",
          categorie: "personal",
        },
        {
          icon: "material-symbols:camera",
          name: "Photography & Videography",
          categorie: "photography",
        },
      ],
    };
  },
};
</script>
