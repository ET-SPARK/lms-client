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
  <Dialog>
    <DialogTrigger as-child>
      <Button variant="outline" class="max-[600px]:text-[12px]">
        <Icon
          name="material-symbols:search"
          class="cursor-pointer mr-2 text-[20px]"
        />
        Search for anything
      </Button>
    </DialogTrigger>
    <DialogContent class="sm:max-w-[425px] max-[600px]:text-[12px]">
      <DialogHeader>
        <DialogTitle>
          <div class="mr-2 flex items-center relative border-b p-2">
            <Icon
              name="material-symbols:search"
              class="absolute left-2 cursor-pointer"
            />
            <div class="grid w-full max-w-sm items-center gap-1.5">
              <Input
                id="text"
                type="text"
                placeholder="Search"
                class="border-none border-input bg-background pl-8 pr-3"
              />
            </div>
          </div>
        </DialogTitle>
      </DialogHeader>
      <!-- search list here -->
    </DialogContent>
  </Dialog>
</template>
