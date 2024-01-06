<template>
  <div
    class="lg:flex lg:justify-center lg:items-center bg-transparent rounded-none min-h-[40vh]"
    id="contact"
  >
    <div class="">
      <div class="w-full justify-center text-center min-h-[30vh]">
        <h1 class="font-bold text-xl md:text-2xl" v-motion-pop-visible>
          Send us a message.
        </h1>
        <form ref="waitlist" action="" method="post" class="">
          <ContactFeedback
            :formFeedback="(formFeedback as string)"
            :isLoading="isLoading"
          />
        </form>
      </div>
    </div>
  </div>
</template>

<style></style>

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
