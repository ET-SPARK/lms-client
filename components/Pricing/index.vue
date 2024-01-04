<template>
  <div class="home-pricing">
    <div class="home-container05">
      <div class="home-container06">
        <h1>Pricing Plans</h1>
        <span class="home-text12">
          <span>
            <span>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. In lorem
              lorem, malesuada in metus vitae, scelerisque accumsan ipsum.
            </span>
          </span>
        </span>
      </div>
      <div class="home-container07">
        <PricingCard></PricingCard>
        <PricingCard text1="$29"></PricingCard>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home-pricing {
  @apply w-full flex justify-center bg-gray-100 p-12;
}
.home-container05 {
  @apply w-full flex p-3 lg:p-8  items-start justify-center;
}
.home-container06 {
  @apply flex-1 flex flex-col items-start mr-8;
}

h1 {
  @apply text-3xl font-bold;
}
.home-text12 {
  @apply text-gray-500 mt-8 text-left mb-8;
}
.home-container07 {
  @apply flex w-1/2 flex-row-reverse;
}

@media (max-width: 991px) {
  .home-container05 {
    @apply items-center flex-col;
  }
  .home-container06 {
    @apply items-center;
  }
  .home-text12 {
    @apply text-center;
  }
  .home-container07 {
    @apply w-full;
  }
}

@media (max-width: 767px) {
  .home-container05 {
    @apply pl-8 pr-8;
  }
  .home-container07 {
    @apply flex-col;
  }
}

@media (max-width: 479px) {
  .home-container05 {
    @apply pt-8 pl-2 pr-2 pb-8;
  }
}
</style>
