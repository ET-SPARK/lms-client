<template>
  <GuestHeader />
  <div class="z-50">
    <div class="text-4xl text-center mt-10 font-bold">Contact Us</div>
    <div class="flex-1 xl:flex lg:flex p-8 justify-center">
      <div class="bg-gray-800 text-white h-auto p-8">
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
        <div class="flex-1 ml-2 items-center">
          <div class="text-4xl font-semibold text-center">
            Send us a Message
          </div>
          <div>
            <form>
              <div class="grid gap-4 py-4">
                <div class="grid grid-cols-4 items-center gap-4">
                  <Label for="name" class="text-right"> Your Name </Label>
                  <Input id="name" type="text" class="col-span-3" />
                </div>
                <div class="grid grid-cols-4 items-center gap-4">
                  <Label for="fatherName" class="text-right">
                    Father Name
                  </Label>
                  <Input id="fatherName" type="text" class="col-span-3" />
                </div>
                <div class="grid grid-cols-4 items-center gap-4">
                  <Label for="number" class="text-right">Phone Number </Label>
                  <Input id="number" type="number" class="col-span-3" />
                </div>
                <div class="grid grid-cols-4 items-center gap-4">
                  <Label for="email" class="text-right">Email </Label>
                  <Input id="email" type="email" class="col-span-3" />
                </div>
                <div class="grid w-full gap-2">
                  <Textarea placeholder="Type your message here." />
                  <Button type="submit">Send message</Button>
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
