<template>
  <Header />
  <div class="border m-10">
    <div class="p-8">
      <div class="mb-4 text-4xl font-bold max-[640px]:text-[26px]">Profile</div>
      <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
        <div>
          <Label>Your Name</Label>
          <Input />
        </div>
        <div><Label>Father Name</Label> <Input /></div>
        <div><Label>Country </Label> <Input /></div>
        <div>
          <Label>City </Label>
          <Input />
        </div>
        <div>
          <Label>Gender </Label>
          <Select>
            <SelectTrigger>
              <SelectValue />
            </SelectTrigger>
            <SelectContent>
              <SelectGroup>
                <SelectItem value="male"> Male </SelectItem>
                <SelectItem value="female"> Female </SelectItem>
              </SelectGroup>
            </SelectContent>
          </Select>
        </div>
        <div>
          <Label>Preferred language </Label>
          <Select>
            <SelectTrigger>
              <SelectValue />
            </SelectTrigger>
            <SelectContent>
              <SelectGroup>
                <SelectItem value="amharic"> Amharic </SelectItem>
                <SelectItem value="english"> English </SelectItem>
              </SelectGroup>
            </SelectContent>
          </Select>
        </div>
        <div>
          <Label>Date of birth</Label>
          <Popover>
            <PopoverTrigger as-child>
              <Button
                :variant="'outline'"
                :class="
                  cn(
                    'w-[280px] justify-start text-left font-normal',
                    !date && 'text-muted-foreground'
                  )
                "
              >
                <CalendarIcon class="mr-2 h-4 w-4" />
                <span>{{ date ? format(date, "PPP") : "Pick a date" }}</span>
              </Button>
            </PopoverTrigger>
            <PopoverContent class="w-auto p-0">
              <Calendar v-model="date" />
            </PopoverContent>
          </Popover>
        </div>
      </div>
      <Button class="mt-4">Save</Button>
    </div>
  </div>
  <FooterAuth />
</template>

<script setup lang="ts">
import { format } from "date-fns";
import { Calendar as CalendarIcon } from "lucide-vue-next";

import { ref } from "vue";
import { cn } from "@/lib/utils";
import { Button } from "@/components/ui/button";
import { Calendar } from "@/components/ui/calendar";
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover";

const date = ref<Date>();

import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select";
</script>
