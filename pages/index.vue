<template>
  <GuestHeader />
  <!-- <Guestfooter /> -->
  <!-- <AuthHeader /> -->
  <!-- <Authfooter /> -->

  <form class="mt-20">
    <div class="flex-1 justify-center xl:flex lg:flex mb-8">
      <div class="mb-4 ml-3">
        <label for="name" class="block text-sm font-medium text-gray-700"
          >Your Name</label
        >
        <input
          type="text"
          id="name"
          name="name"
          class="mt-1 p-2 border rounded-md w-64 lg:w-64 xl:w-64 md:w-[620px]"
          placeholder="Enter your name"
          required
        />
      </div>

      <div class="mb-4 ml-3">
        <label for="fatherName" class="block text-sm font-medium text-gray-700"
          >Father Name</label
        >
        <input
          type="text"
          id="fatherName"
          name="fatherName"
          class="mt-1 p-2 border rounded-md w-64 lg:w-64 xl:w-64 md:w-[620px]"
          placeholder="Enter your father name"
          required
        />
      </div>
    </div>

    <div class="flex-1 justify-center xl:flex lg:flex my-4">
      <!-- Phone Number Section -->
      <div class="mb-4 ml-3">
        <label for="phoneNumber" class="block text-sm font-medium text-gray-700"
          >Phone Number</label
        >
        <div class="relative">
          <Icon
            name="material-symbols:smartphone"
            class="absolute inset-y-0 left-0 pl-2 mt-2 text-gray-500 text-3xl"
          />
          <input
            type="tel"
            id="phoneNumber"
            name="phoneNumber"
            class="pl-10 mt-1 p-2 border rounded-md w-64 lg:w-64 xl:w-64 md:w-[620px]"
            placeholder="Enter your phone number"
            required
          />
        </div>
      </div>

      <!-- Email Section -->
      <div class="mb-4 ml-3">
        <label for="email" class="block text-sm font-medium text-gray-700"
          >Email</label
        >
        <div class="relative">
          <!-- Replace this with the appropriate icon for email -->
          <Icon
            name="material-symbols:alternate-email"
            class="absolute inset-y-0 left-0 pl-2 mt-2 text-gray-500 text-3xl"
          />
          <input
            type="email"
            id="email"
            name="email"
            class="pl-10 mt-1 p-2 border rounded-md w-64 lg:w-64 xl:w-64 md:w-[620px]"
            placeholder="Enter your email address"
            required
          />
        </div>
      </div>
    </div>

    <!-- Message Section -->
    <div class="mb-4 ml-3">
      <label for="message" class="block text-sm font-medium text-gray-700"
        >Message</label
      >
      <textarea
        id="message"
        name="message"
        rows="4"
        class="mt-1 p-2 border rounded-md w-[250px] lg:w-[520px] xl:w-[520px] md:w-[620px]"
        placeholder="Enter your message"
        required
      ></textarea>
    </div>

    <div class="flex-col justify-start">
      <div class="mb-4">
        <label class="inline-flex items-center">
          <input
            type="checkbox"
            class="form-checkbox h-5 w-5 text-blue-500 items-start"
          />
          <span class="ml-2 text-gray-700 text-start"
            >I accept the terms and conditions</span
          >
        </label>
      </div>
      <div>
        <Button type="submit" class="mb-2"> Register </Button>
      </div>
    </div>
  </form>
</template>
<script></script>
