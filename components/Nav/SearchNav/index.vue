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

const courseNavList = [
  {
    icon: "streamline:money-cash-bill-1-billing-bills-payment-finance-cash-currency-money-accounting",
    name: "Accounting & Finance",
    categorie: "accounting",
  },
  {
    icon: "ep:brush",
    name: "Art & Crafts",
    categorie: "art",
  },
  {
    icon: "mdi:brush-off",
    name: "Beauty & Makeup",
    categorie: "beauty",
  },
  {
    icon: "material-symbols:ink-pen-sharp",
    name: "Creatives & Design",
    categorie: "creatives",
  },
  {
    icon: "ic:round-fastfood",
    name: "Food & Beverage",
    categorie: "food",
  },
  {
    icon: "material-symbols:ecg-heart-outline",
    name: "Health & Fitness",
    categorie: "health",
  },
  {
    icon: "streamline:interface-share-mega-phone-1-bullhorn-loud-megaphone-share-speaker-transmit",
    name: "Business & Marketing",
    categorie: "business",
  },
  {
    icon: "ph:code-bold",
    name: "IT & Development",
    categorie: "it",
  },
  {
    icon: "lucide:languages",
    name: "Language & Literature",
    categorie: "language",
  },
  {
    icon: "guidance:office",
    name: "Office Productivity",
    categorie: "office",
  },
  {
    icon: "guidance:meeting-point",
    name: "Personal Development",
    categorie: "personal",
  },
  {
    icon: "material-symbols:camera",
    name: "Photography & Videography",
    categorie: "photography",
  },
];

const SearchCourseName = ref("");
const filteredCourses = computed(() => {
  const search = SearchCourseName.value.toLowerCase();
  return courseNavList.filter((course) =>
    course.name.toLowerCase().includes(search)
  );
});
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
    <DialogContent
      class="sm:w-[425px] lg:max-w-[800px] max-[600px]:text-[12px]"
    >
      <Command>
        <CommandInput
          placeholder="Type a command or search..."
          v-model="SearchCourseName"
        />
        <CommandList>
          <CommandEmpty>No results found.</CommandEmpty>
          <CommandGroup heading="Suggestions">
            <!-- Use v-for directly on CommandItem -->
            <CommandItem
              v-for="course in filteredCourses"
              :key="course.name"
              :value="course.name"
            >
              <NuxtLink
                class="cursor-pointer flex items-center"
                :to="{
                  path: '/courses',
                  query: { categorie: course.categorie },
                }"
              >
                <DialogClose> {{ course.name }}</DialogClose>
              </NuxtLink>
            </CommandItem>
          </CommandGroup>
        </CommandList>
      </Command>
    </DialogContent>
  </Dialog>
</template>
