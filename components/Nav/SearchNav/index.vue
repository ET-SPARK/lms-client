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
import {
  Command,
  CommandDialog,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
  CommandSeparator,
  CommandShortcut,
} from "@/components/ui/command";
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
      <Command>
        <CommandInput placeholder="Type a command or search..." />
        <CommandList>
          <CommandEmpty>No results found.</CommandEmpty>
          <CommandGroup heading="Suggestions">
            <CommandItem value="cloud-computing"> Cloud Computing </CommandItem>
            <CommandItem value="data-science"> Data Science </CommandItem>
            <CommandItem value="full-stack-web-development">
              Full Stack Web Development
            </CommandItem>
            <CommandItem value="machine-learning">
              Machine Learning
            </CommandItem>
          </CommandGroup>
          <CommandSeparator />
          <CommandGroup heading="Settings">
            <CommandItem value="profile"> Profile </CommandItem>
            <CommandItem value="my-course"> My Course </CommandItem>
            <CommandItem value="settings"> Settings </CommandItem>
          </CommandGroup>
        </CommandList>
      </Command>
    </DialogContent>
  </Dialog>
</template>
