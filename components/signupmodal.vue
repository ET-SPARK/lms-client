      <!--  a modal component for the sign up  -->

<template>
  <div
    class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50"
  >
    <div
      class="bg-gray-light p-8 rounded-lg max-w-md w-full shadow-lg relative overflow-y-auto"
    >
      <button
        @click="closeModal"
        class="absolute top-2 right-2 text-gray-500 hover:text-gray-700"
      >
        <svg
          class="h-6 w-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          ></path>
        </svg>
      </button>
      <h2 class="text-3xl font-bold mb-4 text-center">Sign Up</h2>
      <form @submit.prevent="submitForm">
        <div class="mb-4">
          <label for="email" class="block text-gray-700">Email</label>
          <input
            type="email"
            id="email"
            name="email"
            class="w-full border border-gray-300 rounded-md p-2"
          />
        </div>
        <div class="mb-4">
          <label for="phone" class="block text-gray-700">Phone Number</label>
          <input
            type="text"
            id="phone"
            name="phone"
            class="w-full border border-gray-300 rounded-md p-2"
          />
        </div>
        <div class="mb-4">
          <label for="password" class="block text-gray-700">Password</label>
          <input
            type="password"
            id="password"
            name="password"
            class="w-full border border-gray-300 rounded-md p-2"
          />
        </div>
        <button
          type="submit"
          class="bg-blue text-white w-full py-2 rounded-md mb-4"
        >
          Sign Up
        </button>
        <div class="flex items-center justify-center mb-4">
          <span class="border-b border-gray-400 w-1/4"></span>
          <span class="mx-3 text-gray-500">or sign up with</span>
          <span class="border-b border-gray-400 w-1/4"></span>
        </div>
        <div class="flex">
          <div>
                <img src="../static/images/google.svg" class="w-6 h-6" />
              </div>
          <a href="#" class="text-blue ml-2 font-light">sign up with Google</a>
          <a
            href="#"
            class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
            title="google"
          >
            <Icon name="uil:facebook" color="blue" /> </a
          ><a href="#" class="text-blue ml-2 font-light"
            >sign up with facebook</a
          >
        </div>
      </form>
      <p class="text-center mt-4">
        Already have an account? <a href="#" class="text-blue">Log in</a>
      </p>
    </div>
  </div>
</template>
<style>
.text-blue-600 {
  color: #4285f4; /* Set the color to match the original Google icon color */
}
</style>

<script>
export default {
  methods: {
    submitForm() {
      // Add form submission logic here
    },
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
