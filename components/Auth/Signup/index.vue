<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
  DialogClose,
} from "@/components/ui/dialog";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";

const showPassword = ref(false);

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
</script>

<template>
  <Dialog>
    <DialogTrigger as-child>
      <Button variant="outline" class="px-4 py-2 ml-2"> Sign Up </Button>
    </DialogTrigger>
    <DialogContent class="sm:max-w-[425px]">
      <DialogHeader>
        <DialogTitle>Account</DialogTitle>
        <DialogDescription> Create account</DialogDescription>
      </DialogHeader>
      <div>
        <div class="grid grid-cols-2 gap-4">
          <div class="mb-2">
            <Label for="email" class="text-left text-[16px] block">
              Your Name
            </Label>
            <Input type="text" placeholder="Enter your name" />
          </div>
          <div class="mb-2">
            <Label for="password" class="text-left text-[16px] block">
              Father Name
            </Label>
            <Input type="text" placeholder="Enter your father Name" />
          </div>
        </div>
        <div class="mb-2">
          <Label for="email" class="text-left text-[16px] block"> Email </Label>
          <Input type="email" placeholder="Enter your email" />
        </div>
        <div class="mb-2">
          <Label for="number" class="text-left text-[16px] block">
            Phone Number
          </Label>
          <Input type="number" />
        </div>
        <div class="mb-2">
          <Label for="number" class="text-left text-[16px] block">
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
              class="pl-3 mt-1 p-2 border rounded-md w-full text-sm"
              placeholder=""
              required
            />
          </div>
        </div>
        <div class="mb-2">
          <Label for="number" class="text-left text-[16px] block">
            Confirm Password
          </Label>
          <div class="relative">
            <input
              :type="showPassword ? 'text' : 'password'"
              id="password"
              name="password"
              class="pl-3 mt-1 p-2 border rounded-md w-full text-sm"
              placeholder=""
              required
            />
          </div>
        </div>
      </div>
      <DialogFooter>
        <div class="flex-1 text-center">
          <div>
            <DialogClose>
              <Button type="submit" class="mb-2"> Sign Up </Button>
            </DialogClose>
          </div>
          <div class="mb-2">or</div>
          <div>
            <DialogClose>
              <Button type="submit">
                <div>
                  <img
                    src="../../../static/images/google.svg"
                    class="w-6 h-6"
                  />
                </div>
                <div class="ml-4">Continue with Google</div>
              </Button>
            </DialogClose>
          </div>
        </div>
      </DialogFooter>
    </DialogContent>
  </Dialog>
</template>
