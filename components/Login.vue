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
} from "@/components/ui/dialog";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
</script>

<template>
  <div class="z-50">
    <Dialog>
      <DialogTrigger as-child>
        <Button
          variant="outline"
          class="bg-gray-800 border border-blue-500 hover:border-gray-800 text-blue-500 px-4 py-2 ml-2"
        >
          Login
        </Button>
      </DialogTrigger>
      <DialogContent class="sm:max-w-[425px]">
        <DialogHeader>
          <DialogTitle>Account</DialogTitle>
          <DialogDescription> Welcome, Let's get started </DialogDescription>
        </DialogHeader>
        <div class="py-4">
          <div class="flex-1 items-center mb-2">
            <Label for="email" class="text-left mr-2 text-[16px] mb-1">
              Email
            </Label>
            <Input type="email" placeholder="Enter your email" />
            <Label for="password" class="text-left mr-2 text-[16px] mb-2 mt-2">
              Password
            </Label>
            <Input type="password" placeholder="Enter your password" />
          </div>
          <div class="hover:underline cursor-pointer">
            Forgot your password?
          </div>
        </div>
        <DialogFooter>
          <div class="flex-1 text-center">
            <div>
              <Button type="submit" class="mb-2"> Login </Button>
            </div>
            <div class="mb-2">or</div>
            <div>
              <Button type="submit">
                <div>
                  <img src="../static/images/google.svg" class="w-6 h-6" />
                </div>
                <div class="ml-4">Continue with Google</div>
              </Button>
            </div>
          </div>
        </DialogFooter>
      </DialogContent>
    </Dialog>
  </div>
</template>
