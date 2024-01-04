<template>
  <div class="home-banner">
    <div class="home-container01">
      <h1 class="home-text">
        <span>Be the first to get the latest features</span>
      </h1>
      <span class="home-text02">
        <span>
          <span>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non
            volutpat turpis, ut tincidunt lectus. Mauris luctus
          </span>
        </span>
        <span>
          rutrum mi ut rhoncus. Integer in dignissim tortor, id egestas ante.
          Proin at enim purus. Mauris ut felis nisi.
        </span>
      </span>
      <div class="home-container02">
        <input type="text" placeholder="Email here..." class="home-textinput" />
        <button class="home-button">Subscribe</button>
      </div>
    </div>
    <img
      alt="image"
      src="https://images.unsplash.com/photo-1512295767273-ac109ac3acfa?ixid=Mnw5MTMyMXwwfDF8c2VhcmNofDd8fG1pbmltYWxpc20lMjB5ZWxsb3d8ZW58MHx8fHwxNjI2MTg0NjU3&amp;ixlib=rb-1.2.1&amp;w=1000"
      class="home-image"
    />
  </div>
</template>

<style scoped>
.home-banner {
  @apply w-full flex p-12 justify-between  items-center;
}

.home-container01 {
  @apply w-full flex items-start flex-col justify-between;
  @apply mr-24;
}

.home-text {
  @apply text-center font-semibold mb-4;
}

.home-text02 {
  @apply mr-12;
}

.home-container02 {
  @apply flex-shrink-0 w-full h-auto flex mt-8 items-start flex-row justify-start;
}

.home-textinput {
  @apply px-4 py-2  border-gray-800 rounded bg-white text-black text-sm  rounded-md p-2;
}

.home-button {
  @apply inline-block px-4 py-2 border-gray-800 rounded bg-white text-black text-sm transition duration-300 ml-4 border-gray-500;
}

.home-button:hover {
  @apply text-white bg-black;
}

.home-image {
  @apply w-80 h-80 object-cover flex-shrink-0 rounded-lg;
}

@media (max-width: 991px) {
  .home-banner {
    @apply flex-col;
  }

  .home-container01 {
    @apply items-center mr-0 mb-4;
  }

  .home-text02 {
    @apply text-center ml-12;
  }

  .home-container02 {
    @apply justify-center;
  }

  .home-image {
    @apply w-72 h-72;
  }
}

@media (max-width: 767px) {
  .home-banner {
    @apply pl-8 pr-8;
  }

  .home-text02 {
    @apply ml-2 mr-2;
  }
}

@media (max-width: 479px) {
  .home-banner {
    @apply pt-2 pl-4 pr-4 pb-2;
  }

  .home-container02 {
    @apply items-center flex-col;
  }

  .home-button {
    @apply mt-2 ml-0;
  }

  .home-image {
    @apply w-48 h-48;
  }
}
</style>
