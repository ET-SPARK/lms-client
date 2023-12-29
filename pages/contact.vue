<template>
  <GuestHeader />
  <div class="z-50">
    <div class="text-4xl text-center mt-10 font-bold">Contact Us</div>
    <div class="flex-1 xl:flex lg:flex p-8 justify-center">
      <div class="bg-gray-800 text-white h-fit p-8">
        <div class="flex-1 ml-4 mt-4 items-center">
          <div class="text-4xl font-semibold mt-8 mb-4">Info</div>
          <div class="flex-1">
            <div class="flex mt-6">
              <div>
                <Icon
                  name="material-symbols:location-on-rounded"
                  class="text-3xl"
                />
              </div>
              <div class="flex-1 ml-2">
                <div class="text-[12px]">Address</div>
                <div class="text-[14px]">
                  Addis Ababa, 22, Golagol Building 4th floor, 405
                </div>
              </div>
            </div>
            <div class="flex mt-6">
              <div>
                <Icon name="material-symbols:call" class="text-3xl" />
              </div>
              <div class="flex-1 ml-2">
                <div class="text-[12px]">Phone number</div>
                <div class="text-[14px]">+251 9XXXXXXXXX</div>
              </div>
            </div>
            <div class="flex mt-6">
              <div>
                <Icon
                  name="material-symbols:alternate-email"
                  class="text-3xl"
                />
              </div>
              <div class="flex-1 ml-2">
                <div class="text-[12px]">Email</div>
                <div class="text-[14px]">hi@adninetlms.com</div>
              </div>
            </div>
          </div>

          <div class="flex mt-16 mb-4">
            <a
              href="#"
              class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
              title="LinkedIn"
            >
              <Icon name="uil:linkedin" color="blue" size="28" />
            </a>
            <a
              href="#"
              class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
              title="Youtube"
            >
              <Icon name="uil:youtube" color="red" size="28" />
            </a>
            <a
              href="#"
              class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
              title="Facebook"
            >
              <Icon name="uil:facebook" color="blue" size="28" />
            </a>

            <a
              href="#"
              class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
              title="Instagram"
            >
              <Icon name="uil:instagram" color="red" size="28" />
            </a>
            <a
              href="#"
              class="text-gray-500 hover:text-gray-900 dark:hover:text-white ms-5"
              title="Telegram"
            >
              <Icon name="uil:telegram" color="blue" size="28" />
            </a>
          </div>
        </div>
      </div>
      <div class="text-gray-800">
        <div class="flex-1 ml-8 items-center">
          <div class="text-4xl font-semibold mt-4 mb-4 text-center">
            Send us a Message
          </div>
          <div>
            <form class="mt-20">
              <div class="flex-1 justify-center xl:flex lg:flex mb-8">
                <div class="mb-4 ml-3">
                  <label
                    for="name"
                    class="block text-sm font-medium text-gray-700"
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
                  <label
                    for="fatherName"
                    class="block text-sm font-medium text-gray-700"
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
                  <label
                    for="phoneNumber"
                    class="block text-sm font-medium text-gray-700"
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
                  <label
                    for="email"
                    class="block text-sm font-medium text-gray-700"
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
                <label
                  for="message"
                  class="block text-sm font-medium text-gray-700"
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
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- <Guestfooter /> -->
</template>
