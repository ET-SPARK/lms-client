//fotter for users that dosen't loged in or for the guest users

<template>
  <footer
    class="bg-gray-900 text-white text-center py-4 absolute bottom-0-0 w-full"
  >
    <div>
      <form action="">
        <div
          class="gird-cols-1 grid items-center justify-center gap-4 md:grid-cols-3"
        >
          <div class="md:mb-6 md:ml-auto">
            <p class="">
              <strong>Sign up for our Lms Courses</strong>
            </p>
          </div>

          <!-- Newsletter sign-up input field -->
          <div class="relative md:mb-6" data-te-input-wrapper-init>
            <input
              type="text"
              class="bg-gray-light block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] text-neutral-200 outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200"
              id="exampleFormControlInput1"
              placeholder="Enter your Email address"
            />
          </div>

          <!-- Newsletter sign-up submit button -->
          <div class="mb-6 md:mr-auto">
            <button
              type="submit"
              class="bg-orange inline-block rounded border-2 border-neutral-50 px-6 pb-[6px] pt-2 text-xs font-medium uppercase leading-normal text-neutral-50 transition duration-150 ease-in-out hover:border-neutral-100 hover:bg-neutral-500 hover:bg-opacity-10 hover:text-neutral-100 focus:border-neutral-100 focus:text-neutral-100 focus:outline-none focus:ring-0 active:border-neutral-200 active:text-neutral-200 dark:hover:bg-neutral-100 dark:hover:bg-opacity-10"
              data-te-ripple-init
              data-te-ripple-color="light"
            >
              Subscribe
            </button>
          </div>
        </div>
      </form>
    </div>

    <div class="mx-auto w-full max-w-screen-xl p-4 py-6 lg:py-8">
      <div class="md:flex md:justify-between">
        <div class="mb-6 md:mb-0">
          <a href="https://andinetsolutions.com/" class="flex items-center">
            <img
              src="../../static/images/andinet_logo.jpg"
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
                <NuxtLink to="/contact" class="hover:underline"
                  >Contact Us</NuxtLink
                >
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
          >© 2023
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
  // Your component logic here
};
</script>
