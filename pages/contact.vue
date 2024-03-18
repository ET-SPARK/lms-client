<template>
  <Header />

  <div class="">
    <div
      class="text-4xl text-center mt-10 font-bold max-[600px]:text-[20px] max-[600px]:mt-4 uppercase"
    >
      Contact Us
    </div>
    <div class="flex-1 xl:flex lg:flex p-8 max-[600px]:py-4 justify-center">
      <div class="bg-secondary h-auto p-8">
        <div class="flex-1 ml-2 mt-4 items-center">
          <div class="text-4xl font-semibold mt-8 mb-4 max-[600px]:text-[16px]">
            Info
          </div>
          <div class="flex-1">
            <div class="flex mt-4">
              <div>
                <Icon
                  name="material-symbols:location-on-rounded"
                  class="text-3xl max-[600px]:text-[14px]"
                />
              </div>
              <div class="flex-1 ml-2">
                <div
                  class="text-[12px] max-[600px]:text-[10px] uppercase text-black"
                >
                  Address
                </div>
                <div class="text-[14px] max-[600px]:text-[12px]">
                  Addis Ababa, 22, Golagol Building 4th floor, 405
                </div>
              </div>
            </div>
            <div class="flex mt-4">
              <div>
                <Icon
                  name="material-symbols:call"
                  class="text-3xl max-[600px]:text-[14px]"
                />
              </div>
              <div class="flex-1 ml-2">
                <div
                  class="text-[12px] max-[600px]:text-[10px] uppercase text-black"
                >
                  Phone number
                </div>
                <div class="text-[14px] max-[600px]:text-[12px]">
                  +251 9XXXXXXXXX
                </div>
              </div>
            </div>
            <div class="flex mt-4">
              <div>
                <Icon
                  name="material-symbols:alternate-email"
                  class="text-3xl max-[600px]:text-[14px]"
                />
              </div>
              <div class="flex-1 ml-2">
                <div
                  class="text-[12px] max-[600px]:text-[10px] uppercase text-black"
                >
                  Email
                </div>
                <div class="text-[14px] max-[600px]:text-[12px]">
                  hi@adninetlms.com
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="flex justify-between py-8 mt-2">
          <div>
            <Icon
              name="tabler:brand-facebook"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-instagram"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="pajamas:twitter"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-telegram"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-youtube"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-linkedin"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-tiktok"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[12px]"
            />
          </div>
        </div>
      </div>
      <div class="p-4">
        <div class="flex-1 ml-2 items-center">
          <div
            class="text-4xl font-semibold text-center max-[600px]:text-[20px]"
          >
            Send us a Message
          </div>
          <div>
            <form>
              <div class="grid w-full max-w-xl items-center gap-1.5">
                <Label for="text" class="max-[600px]:text-[12px]">Name</Label>
                <Input id="text" type="text" />
              </div>
              <div class="grid w-full max-w-sm items-center gap-1.5">
                <Label for="email" class="max-[600px]:text-[12px]">Email</Label>
                <Input id="email" type="email" />
              </div>
              <div class="grid w-full max-w-sm items-center gap-1.5">
                <Label for="number" class="max-[600px]:text-[12px]"
                  >Phone Number</Label
                >
                <Input id="number" type="number" />
              </div>
              <div class="grid w-full gap-1.5">
                <Label for="message-2" class="max-[600px]:text-[12px]"
                  >Your message</Label
                >
                <Textarea id="message-2" />
              </div>
              <div class="flex items-center space-x-2 mt-2">
                <Checkbox id="terms" />
                <label
                  for="terms"
                  class="text-sm font-medium leading-none peer-disabled:cursor-not-allowed peer-disabled:opacity-70 max-[600px]:text-[12px]"
                >
                  Accept terms and conditions
                </label>
              </div>
              <Button class="mt-2 max-[600px]:text-[12px]">Send message</Button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>

  <FooterGuest />
</template>
