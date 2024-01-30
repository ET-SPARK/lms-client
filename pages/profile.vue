<template>
  <HeaderAuth />
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
          <Calendar v-model="date" class="rounded-md border h-[350px]" />
        </div>
      </div>
      <Button class="mt-4">Save</Button>
    </div>
  </div>
  <FooterAuth />
</template>

<script setup lang="ts">
import { Calendar } from "@/components/ui/calendar";
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select";

const date = ref(new Date());
</script>
