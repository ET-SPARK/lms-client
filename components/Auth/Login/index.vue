<template>
  <div class="z-50">
    <Dialog>
      <DialogTrigger as-child>
        <Button variant="outline" class="px-4 py-2 ml-2"> Login </Button>
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
          <!-- forgot password -->
          <div class="hover:underline cursor-pointer">
            <Dialog>
              <DialogTrigger as-child>
                <Button variant="outline"> Forgot your password? </Button>
              </DialogTrigger>
              <DialogContent class="sm:max-w-[425px]">
                <DialogHeader>
                  <DialogTitle>Account</DialogTitle>
                  <DialogDescription> Reset password </DialogDescription>
                </DialogHeader>
                <div class="grid gap-4 py-4">
                  <div class="flex-1 items-center mb-2">
                    <Label for="email" class="text-left mr-2 text-[16px] mb-1">
                      Email
                    </Label>
                    <Input type="email" placeholder="Enter your email" />
                  </div>
                </div>
                <DialogFooter>
                  <!-- verify and set password -->
                  <Dialog>
                    <DialogTrigger as-child>
                      <Button type="submit"> Send Verification </Button>
                    </DialogTrigger>
                    <DialogContent class="sm:max-w-[425px]">
                      <DialogHeader>
                        <DialogTitle>Account</DialogTitle>
                        <DialogDescription>
                          Adinet lms sent you a verification code to
                          abebe@gmail.com, Please enter your verification code
                          and new password here
                        </DialogDescription>
                      </DialogHeader>
                      <div class="grid gap-4 py-4">
                        <div class="flex-1 items-center mb-2">
                          <Label
                            for="email"
                            class="text-left mr-2 text-[16px] mb-1"
                          >
                          </Label>
                          <form class="" @submit="onSubmit">
                            <FormField v-slot="{ componentField }" name="pin">
                              <FormItem>
                                <FormLabel>OTP Verification code</FormLabel>
                                <FormControl>
                                  <PinInput
                                    id="pin-input"
                                    placeholder="○"
                                    class="flex gap-2 items-center mt-1"
                                    otp
                                    type="number"
                                    :name="componentField.name"
                                    @complete="handleComplete"
                                    @update:model-value="
                                      (arrStr) => {
                                        setValues({
                                          pin: arrStr.filter(Boolean),
                                        });
                                      }
                                    "
                                  >
                                    <PinInputInput
                                      v-for="(id, index) in 5"
                                      :key="id"
                                      :index="index"
                                    />
                                  </PinInput>
                                </FormControl>
                                <FormMessage />
                              </FormItem>
                            </FormField>
                          </form>
                          <Label
                            for="email"
                            class="text-left mr-2 text-[16px] mb-1 mt-2"
                          >
                            New password
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
                              placeholder=""
                              required
                            />
                          </div>
                        </div>
                      </div>
                      <div class="flex justify-between">
                        <DialogFooter>
                          <Button type="submit"> Resend </Button>
                        </DialogFooter>
                        <DialogClose>
                          <DialogFooter>
                            <Button type="submit"> Set Password </Button>
                          </DialogFooter>
                        </DialogClose>
                      </div>
                    </DialogContent>
                  </Dialog>
                </DialogFooter>
              </DialogContent>
            </Dialog>
          </div>
        </div>
        <DialogFooter>
          <div class="flex-1 text-center">
            <div>
              <DialogClose>
                <Button type="submit" class="mb-2"> Login </Button></DialogClose
              >
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
  </div>
</template>

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
const showPassword = ref(false);

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
import { h } from "vue";
import { useForm } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";
import { PinInput, PinInputInput } from "@/components/ui/pin-input";
import {
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { toast } from "@/components/ui/toast";

const formSchema = toTypedSchema(
  z.object({
    pin: z.array(z.coerce.string()).length(5, { message: "Invalid input" }),
  })
);

const { handleSubmit, setValues } = useForm({
  validationSchema: formSchema,
  initialValues: {
    pin: [],
  },
});

const onSubmit = handleSubmit(({ pin }) => {
  toast({
    title: "You submitted the following values:",
    description: h(
      "pre",
      { class: "mt-2 w-[340px] rounded-md bg-slate-950 p-4" },
      h("code", { class: "text-white" }, JSON.stringify(pin.join(""), null, 2))
    ),
  });
});

const handleComplete = (e: string[]) => console.log(e.join(""));
</script>
