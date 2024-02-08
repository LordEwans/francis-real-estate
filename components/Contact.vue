<template>
  <div
    class="flex justify-center items-center bg-transparent rounded-none min-h-[40vh]"
    id="contact"
  >
    <div class="w-[96%] md:max-w-xl lg:max-w-4xl">
      <div class="w-full justify-center text-center min-h-[30vh]">
        <h1 class="font-bold text-xl md:text-2xl mb-4" v-motion-pop-visible>
          Send us a message.
        </h1>
        <form ref="waitlist" action="" method="post" class="">
          <p class="text-left">Email.</p>
          <input
            type="email"
            class="text-gray-800 w-full mb-2 h-12 rounded-lg input"
            placeholder="johndoe@gmail.com"
          />
          <p class="text-left">Message.</p>
          <textarea
            name=""
            id=""
            cols="30"
            rows="10"
            class="resize-none text-gray-800 h-52 w-full rounded-lg input"
            placeholder="Estate Inquiry.
I have plans to get a new property and I'm hoping to find one with a budget of [amount] in [location].
"
          ></textarea>
          <button
            class="btn bg-gray-700 border-gray-700 text-white btn-block mt-6"
            @click.prevent=""
          >
            Send Message
          </button>
          <ContactFeedback
            :formFeedback="(formFeedback as string)"
            :isLoading="isLoading"
          />
        </form>
      </div>
    </div>
  </div>
</template>

<style>
.input {
  @apply bg-white;
}
</style>

<script setup lang="ts">
import { ref } from "vue";
type FormFeedbackType =
  | "incomplete"
  | "consent"
  | "invalid"
  | "error"
  | "success"
  | null;

// proxy type
type ProxyType = {
  status: number;
  message: string;
  data: {
    error?: string;
    id?: {
      InsertedID: string;
    };
  };
};

// refs
const email = ref("");
const consent = ref(true);
const isLoading = ref(false);
const formFeedback: Ref<FormFeedbackType> = ref(null);
const success = ref(true);

// email submit function
const submitEmail = async () => {
  isLoading.value = true;
  formFeedback.value = null;

  email.value = email.value.trim();

  const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i;
  if (!email.value.trim()) {
    formFeedback.value = "incomplete";
    isLoading.value = false;
    return;
  } else if (email.value && !regex.test(email.value)) {
    formFeedback.value = "invalid";
    success.value = false;
    isLoading.value = false;
    return;
  } else if (!consent.value) {
    formFeedback.value = "consent";
    success.value = false;
    isLoading.value = false;
    return;
  } else {
    // wait 4 seconds then submit
    setTimeout(async () => {
      try {
        const { data: proxy } = await useFetch(
          "https://mailclient.onrender.com/add",
          {
            method: "post",
            body: { address: email },
          }
        );
        const data: Ref<ProxyType> = ref(proxy) as Ref<ProxyType>;

        email.value = "";
        success.value = true;
        isLoading.value = false;
        data.value.message == "error"
          ? (formFeedback.value = "error")
          : (formFeedback.value = "success");
      } catch (error) {
        success.value = false;
        isLoading.value = false;
        formFeedback.value = "error";
      }
    }, 4000);
  }
};
</script>
