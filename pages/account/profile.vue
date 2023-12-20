<template>
  <Header />
  <div class="bg-gray-100 m-8 p-8">
    <div class="font-bold text-4xl">Profile</div>
    <form>
      <div>
        <div class="mt-10 flex justify-between">
          <div class="">
            <label class="block text-l font-medium"
              >Your Name<sup class="text-red-500 text-[18px]">*</sup></label
            >
            <input
              type="text"
              id="name"
              name="name"
              class="mt-1 p-2 border rounded-md px-6 w-[350px]"
              placeholder="Enter your name"
              required
            />
          </div>
          <div class="">
            <label class="block text-l font-medium"
              >Father name<sup class="text-red-500 text-[18px]">*</sup></label
            >
            <input
              type="text"
              id="name"
              name="name"
              class="mt-1 p-2 border rounded-md px-6 w-[400px]"
              placeholder="Enter your Father name"
              required
            />
          </div>
          <div class="">
            <label class="block text-l font-medium">Country</label>
            <input
              type="text"
              id="name"
              name="name"
              class="mt-1 p-2 border rounded-md px-6 w-[400px]"
              placeholder="Enter your Country"
              required
            />
          </div>
        </div>
        <div class="mt-10 flex justify-start">
          <div class="">
            <label class="block text-l font-medium">City</label>
            <input
              type="text"
              id="name"
              name="name"
              class="mt-1 p-2 border rounded-md px-6 w-[350px]"
              placeholder="Enter your City"
              required
            />
          </div>
          <div class="flex ml-10">
            <div class="">
              <label class="block text-l font-medium"
                >Gender<sup class="text-red-500 text-[18px]">*</sup></label
              >
              <select
                id="gender"
                name="gender"
                class="mt-1 p-2 border rounded-md px-6 w-[300px]"
                required
              >
                <option value="" disabled selected class="text-gray-400">
                  Select your gender
                </option>
                <option value="male" class="option-gray">Male</option>
                <option value="female" class="option-gray">Female</option>
              </select>
            </div>
            <div class="ml-20">
              <label class="block text-l font-medium">Preferred language</label>
              <select
                id="gender"
                name="gender"
                class="mt-1 p-2 border rounded-md px-6 w-[300px]"
                required
              >
                <option value="" disabled selected>Select your language</option>
                <option value="male" class="option-gray">Amharic</option>
                <option value="female" class="option-gray">English</option>
              </select>
            </div>
          </div>
        </div>
        <div class="mt-10 flex justify-between">
          <div class="">
            <label class="block text-l font-medium">Date of birth </label>
            <input
              type="date"
              id="name"
              name="name"
              class="mt-1 p-2 border rounded-md px-6 w-[350px]"
              required
            />
          </div>
        </div>
      </div>
      <div class="mt-8 flex justify-center">
        <button
          type="submit"
          class="bg-blue-500 hover:bg-blue-600 text-white text-xl py-2 px-6 rounded-sm"
        >
          Save
        </button>
      </div>
    </form>
  </div>
  <Footer />
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
