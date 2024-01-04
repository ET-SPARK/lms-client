<template>
  <div class="home-features">
    <h1 class="home-text07">
      <span>Discover our</span>
      <br />
      <span>unique features</span>
    </h1>
    <div class="home-separator"></div>
    <div class="home-container03">
      <div class="home-container04 grid grid-cols-2 gap-4">
        <FeatureCard rootClassName="rootClassName1"></FeatureCard>
        <FeatureCard rootClassName="rootClassName4"></FeatureCard>
        <FeatureCard rootClassName="rootClassName3"></FeatureCard>
        <FeatureCard rootClassName="rootClassName2"></FeatureCard>
      </div>
      <img
        alt="image"
        src="https://images.unsplash.com/photo-1471086569966-db3eebc25a59?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDIzfHxtaW5pbWFsaXNtfGVufDB8fHx8MTYyNjQ0NTY1Nw&amp;ixlib=rb-1.2.1&amp;h=1000"
        class="home-image1 ml-14 rounded-full"
      />
    </div>
  </div>
</template>

<style scoped>
.home-features {
  @apply w-full flex flex-col p-12;
}

.home-text07 {
  @apply text-3xl font-semibold mb-8;
}

.home-separator {
  @apply w-24 h-2 bg-gray-500;
}

.home-container03 {
  @apply flex-shrink-0 w-full flex items-center flex-row justify-between mt-8;
}

.home-container04 {
  @apply grid grid-cols-2 gap-4;
}

.home-image1 {
  @apply w-72 h-72 object-cover flex-shrink-0 ml-14 rounded-full;
}

@media (max-width: 991px) {
  .home-features {
    @apply items-center;
  }

  .home-container03 {
    @apply flex-col;
  }

  .home-image1 {
    @apply w-48 h-48 mt-8 ml-0;
  }
}

@media (max-width: 767px) {
  .home-features {
    @apply pl-8 pr-8;
  }

  .home-text07 {
    @apply text-center;
  }

  .home-container03 {
    @apply flex-col;
  }
}

@media (max-width: 479px) {
  .home-features {
    @apply pt-8 pl-4 pr-4 pb-8;
  }

  .home-container04 {
    @apply grid-cols-1;
  }

  .home-image1 {
    @apply w-60 h-60;
  }
}

@media (max-width: 350px) {
  .home-text07 {
    @apply text-2xl;
  }
}
</style>
