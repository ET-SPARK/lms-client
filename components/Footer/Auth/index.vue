//fotter for users that have loged in

<template>
  <footer
    class="dark:bg-background absolute bottom-0-0 pt-6 text-center w-full overflow-x-auto border-t"
  >
    <div class="mx-auto w-full max-w-screen-xl p-4 py-6 lg:py-8">
      <div class="md:flex md:justify-between">
        <div class="mb-6 md:mb-0 ml-10 sm:ml-1">
          <a href="https://andinetsolutions.com/" class="flex items-center">
            <img
              src="../../../static/images/andinet_logo.jpg"
              class="h-12 sm:h-28 me-3 rounded-full"
              alt="Andinet lms logo"
            />
            <span class="self-center text-2xl font-semibold whitespace-nowrap"
              >Andinet LMS</span
            >
          </a>
        </div>
        <div class="grid grid-cols-2 gap-8 sm:gap-6 sm:grid-cols-3">
          <div>
            <h2 class="mb-6 text-sm font-semibold uppercase">HELP CENTER</h2>
            <ul class="font-medium">
              <li class="mb-4">
                <a href="#" class="hover:underline">Contact Us</a>
              </li>
              <li class="mb-4">
                <a href="#" class="hover:underline">Help</a>
              </li>
              <li class="mb-4">
                <a href="#" class="hover:underline">FAQs</a>
              </li>
              <li>
                <a href="#" class="hover:underline"> customer support</a>
              </li>
            </ul>
          </div>
          <div>
            <h2 class="mb-6 text-sm font-semibold uppercase">Follow us</h2>
            <ul class="font-medium">
              <li class="mb-4">
                <a href="#" class="hover:underline">Youtube</a>
              </li>
              <li class="mb-4">
                <a
                  href="https://www.linkedin.com/in/andinet-buisness-group-436ab7258/?originalSubdomain=et"
                  class="hover:underline"
                  >Linkedin</a
                >
              </li>
              <li>
                <a href="#" class="hover:underline">Blogs</a>
              </li>
            </ul>
          </div>
          <div>
            <h2 class="mb-6 text-sm font-semibold uppercase">Legal</h2>
            <ul class="font-medium">
              <li class="mb-4">
                <a href="#" class="hover:underline">Privacy Policy</a>
              </li>
              <li>
                <a href="#" class="hover:underline">Terms &amp; Conditions</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <hr
        class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8"
      />
      <div class="sm:flex sm:items-center sm:justify-between">
        <span class="text-l max-[600px]:text-sm sm:text-center"
          >© {{ currentYear }}
          <a href="https://andinetsolutions.com/" class="hover:underline"
            >Andinet Business Group</a
          >. All Rights Reserved.
        </span>
        <div class="flex justify-between py-8 mt-2">
          <div>
            <Icon
              name="tabler:brand-facebook"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-instagram"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="pajamas:twitter"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-telegram"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-youtube"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-linkedin"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
          <div>
            <Icon
              name="tabler:brand-tiktok"
              class="bg-#212F3D cursor-pointer ml-3 text-3xl max-[600px]:text-[16px]"
            />
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style>
@media (max-width: 640px) {
  .footer {
    height: 200px; /* Adjust the height as needed */
  }
}
</style>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>
