<template>
  <Header />
  <div class="bg-gray-100 m-8 p-8">
    <div class="flex justify-between p-10">
      <div>
        <p class="text-4xl font-bold">Contact Us</p>
        <div class="flex items-center mt-6">
          <div>
            <Icon
              name="material-symbols:mail"
              class="cursor-pointer text-xl"
              color="black"
            />
          </div>
          <div class="flex-1 ml-4">
            <div class="text-sm">Email</div>
            <div class="text-blue-500">abc@gmail.com</div>
          </div>
        </div>
        <div class="flex items-center mt-6">
          <div>
            <Icon
              name="material-symbols:call-sharp"
              class="cursor-pointer text-xl"
              color="black"
            />
          </div>
          <div class="flex-1 ml-4">
            <div class="text-sm">Phone</div>
            <div class="text-blue-500">+251-9xxxxxxxx</div>
          </div>
        </div>
        <div class="flex items-center mt-6">
          <div>
            <Icon
              name="material-symbols:location-on"
              class="cursor-pointer text-xl"
              color="black"
            />
          </div>
          <div class="flex-1 ml-4">
            <div class="text-sm">Address</div>
            <div class="text-blue-500">Addis Ababa, Ethiopia</div>
          </div>
        </div>
        <div class="flex items-center mt-6">
          <div>
            <Icon
              name="material-symbols:sunny"
              class="cursor-pointer text-xl"
              color="black"
            />
          </div>
          <div class="flex-1 ml-4">
            <div class="text-sm">Office hours</div>
            <div class="text-blue-500">9 a.m – 5 p.m</div>
          </div>
        </div>
      </div>
      <div>
        <img
          src="https://images.pexels.com/photos/4144294/pexels-photo-4144294.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
          class="w-[500px]"
        />
      </div>
    </div>
  </div>
  <Footer />
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
