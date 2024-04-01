<script setup lang="ts">
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
const showPassword = ref(false);

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
</script>

<template>
  <div class="border rounded-xl flex max-[820px]:flex-col m-4">
    <div
      class="bg-secondary px-8 max-[820px]:px-2 border-r w-1/2 max-[820px]:w-full max-[820px]:border-b max-[820px]:border-r-0 py-8 flex-col items-center justify-center"
    >
      <div class="flex items-center">
        <div>
          <img
            class="w-16 h-16 cursor-pointer rounded-full mr-4"
            src="../../../static/images/andinet_logo.jpg"
          />
        </div>
      </div>
      <div
        class="font-bold text-xl text-center max-[640px]:text-sm max-[640px]:mt-2"
      >
        Join Andinet Academy to activate your teaching
      </div>
      <div class="font-semibold text-xl text-center max-[640px]:text-sm">
        Log in to Andinet Academy to get started!
      </div>

      <div>
        <img
          src="../../../static/images/landImg.png"
          class="w-full h-[450px] max-[640px]:h-[350px] cursor-pointer rounded-full mr-4"
        />
      </div>
    </div>
    <div
      class="py-8 px-8 max-[820px]:px-2 w-1/2 max-[820px]:w-full pl-4 max-[820px]:pl-0"
    >
      <div class="text-2xl font-bold text-center max-[640px]:text-lg">
        Create an account
      </div>
      <div
        class="flex-1 items-center mb-2 mt-16 max-[820px]:mt-2 px-10 max-[820px]:px-2"
      >
        <Label
          for="name"
          class="text-left mr-2 text-[16px] mb-1 max-[640px]:text-sm"
        >
          Full Name
        </Label>
        <Input type="text" placeholder="Enter your full name" />
        <Label
          for="number"
          class="text-left mr-2 text-[16px] mb-1 max-[640px]:text-sm"
        >
          Phone Number
        </Label>
        <Input type="text" placeholder="Enter your phone number" />
        <Label
          for="email"
          class="text-left mr-2 text-[16px] mb-1 max-[640px]:text-sm"
        >
          Email
        </Label>
        <Input type="email" placeholder="Enter your email" />
        <Label
          for="password"
          class="text-left mr-2 text-[16px] mb-2 mt-2 max-[640px]:text-sm"
        >
          Password
        </Label>
        <div class="relative">
          <Icon
            v-if="showPassword"
            @click="togglePasswordVisibility"
            name="material-symbols:visibility-lock"
            class="absolute inset-y-0 right-0 pr-2 mt-2 text-gray-500 text-3xl"
          />
          <Icon
            v-else
            @click="togglePasswordVisibility"
            name="material-symbols:visibility"
            class="absolute inset-y-0 right-0 pr-2 mt-2 text-gray-500 text-3xl cursor-pointer"
          />
          <input
            :type="showPassword ? 'text' : 'password'"
            id="password"
            name="password"
            class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-1 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
            placeholder="Enter your password"
            required
          />
        </div>
      </div>

      <div class="flex justify-center items-center mt-4">
        <NuxtLink to="/mycourse">
          <Button type="submit" class="mb-2">
            <div class="flexs">Sign up</div>
          </Button>
        </NuxtLink>
      </div>

      <div class="relative mt-4">
        <div class="absolute inset-0 flex items-center">
          <span class="w-full border-t" />
        </div>
        <div class="relative flex justify-center text-xs uppercase">
          <span class="bg-background px-2 text-muted-foreground"> Or </span>
        </div>
      </div>
      <div class="flex justify-center items-center mt-4">
        <Button type="submit">
          <div>
            <img src="../../../static/images/google.svg" class="w-6 h-6" />
          </div>
          <div class="ml-4 max-[640px]:text-sm">Continue with Google</div>
        </Button>
      </div>
      <div class="mt-4 max-[640px]:text-sm">
        <p
          class="px-8 max-[820px]:px-2 text-center text-sm text-muted-foreground"
        >
          By clicking continue, you agree to our
          <a
            href="/terms"
            class="underline underline-offset-4 hover:text-primary"
          >
            Terms of Service
          </a>
          and
          <a
            href="/privacy"
            class="underline underline-offset-4 hover:text-primary"
          >
            Privacy Policy
          </a>
          .
        </p>
      </div>
      <NuxtLink to="/login">
        <div class="mt-4 text-center hover:underline max-[640px]:text-sm">
          Already have an account?
        </div>
      </NuxtLink>
    </div>
  </div>
</template>
