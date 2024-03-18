<script setup lang="ts">
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
import { Button } from "@/components/ui/button";
</script>

<template>
  <Dialog>
    <DialogTrigger class="w-full">
      <Button class="w-full">Buy Course</Button>
    </DialogTrigger>
    <DialogContent>
      <DialogHeader>
        <DialogTitle>Course Payment</DialogTitle>
        <DialogDescription>
          <div class="border flex justify-between p-4">
            <div class="text-start">
              <div class="text-xl">Price</div>
              <div class="text-[11px]">Full access to the course</div>
            </div>
            <div class="text-center">
              <div class="text-[11px]">ETB</div>
              <div class="text-2xl font-bold">2500</div>
            </div>
          </div>
          <div class="border p-4 mt-2">
            <div class="border-b pb-2">Pay via CBE or Telebirr</div>
            <div>CBE Account Number: 1000---------</div>
            <div>Telebirr Phone Number: 09--------</div>
          </div>
          <div class="border p-4 mt-2">
            After completing the payment, please send a screenshot of
            transaction to this Telegram account:
            <a href="http://t.me/____" target="_blank" class="hover:underline"
              >http://t.me/____</a
            >
          </div>
          <div class="mt-4">
            <div class="text-sm">
              If you have any payment issues, please
              <span class="hover:underline">Contact us</span>
            </div>
          </div>
        </DialogDescription>
      </DialogHeader>

      <DialogFooter>
        <div class="flex-col justify-center items-center">
          <div>
            <DialogClose>
              <Button class="w-full">Enroll Now</Button></DialogClose
            >
          </div>
        </div>
      </DialogFooter>
    </DialogContent>
  </Dialog>
</template>
