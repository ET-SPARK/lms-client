//fotter for users that dosen't loged in or for the guest users

<template>
  <footer
    class="bg-gray-800 text-white absolute bottom-0-0 pt-6 text-center w-full overflow-x-auto"
  >
    <div>
      <form action="">
        <div
          class="gird-cols-1 grid items-center justify-center gap-4 md:grid-cols-3"
        >
          <div class="md:mb-6 md:ml-auto">
            <p class="max-[600px]:text-[14px]">Subscribe our Lms News</p>
          </div>

          <div class="flex w-full max-w-sm items-center gap-1.5">
            <Input id="email" type="email" placeholder="Email" />
            <Button type="submit" class="max-[600px]:text-[14px]">
              Subscribe
            </Button>
          </div>
        </div>
      </form>
    </div>

    <div class="mx-auto w-full max-w-screen-xl p-4 py-6 lg:py-8">
      <div class="md:flex md:justify-between">
        <div class="mb-6 md:mb-0 ml-10 sm:ml-1">
          <a href="https://andinetsolutions.com/" class="flex items-center">
            <img
              src="../../../static/images/andinet_logo.jpg"
              class="h-12 sm:h-28 me-3"
              alt="Andinet lms logo"
            />
            <span
              class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white"
              >Andinet Lms</span
            >
          </a>
        </div>
        <div class="grid grid-cols-2 gap-8 sm:gap-6 sm:grid-cols-4">
          <div>
            <h2
              class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white"
            >
              HELP CENTER
            </h2>
            <ul class="text-gray-500 dark:text-gray-400 font-medium">
              <li class="mb-4">
                <a href="#" class="hover:underline">Contact Us</a>
              </li>
              <li class="mb-4">
                <a href="#" class="hover:underline">Help</a>
              </li>

              <li>
                <a href="#" class="hover:underline"> customer support</a>
              </li>
            </ul>
          </div>
          <div>
            <h2
              class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white"
            >
              Resources
            </h2>
            <ul class="text-gray-500 dark:text-gray-400 font-medium">
              <li class="mb-4">
                <a href="#" class="hover:underline">User Guides</a>
              </li>
              <li class="mb-4">
                <a href="#" class="hover:underline">Webinars</a>
              </li>
              <li>
                <a href="#" class="hover:underline">Benifts</a>
              </li>
            </ul>
          </div>
          <div>
            <h2
              class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white"
            >
              Follow us
            </h2>
            <ul class="text-gray-500 dark:text-gray-400 font-medium">
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
                <a href="#" class="hover:underline">sign-up</a>
              </li>
            </ul>
          </div>
          <div>
            <h2
              class="mb-6 text-sm font-semibold text-gray-900 uppercase dark:text-white"
            >
              Legal
            </h2>
            <ul class="text-gray-500 dark:text-gray-400 font-medium">
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
        <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400"
          >© {{ currentYear }}
          <a href="https://andinetsolutions.com/" class="hover:underline"
            >Andinet Business Group</a
          >. All Rights Reserved.
        </span>
        <div class="flex mt-4 sm:justify-center sm:mt-0">
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
  </footer>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>
