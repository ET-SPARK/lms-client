<template>
  <HeaderAuth />
  <div class="border">
    <div>Profile</div>
    <div>
      <Label>Your Name</Label>
      <Input />
      <Label>Father Name</Label>
      <Input />
      <Label>Country </Label>
      <Input />
      <Label>City </Label>
      <Input />
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
  </div>
  <FooterAuth />
</template>

<script setup lang="ts">
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
