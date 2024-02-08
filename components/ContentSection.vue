<template>
  <div class="min-h-[75vh] flex items-center border-b rounded-none">
    <div>
      <h2
        class="capitalize text-3xl md:text-4xl lg:text-6xl leading-[1.1] font-extrabold"
        v-motion-slide-visible-left
      >
        {{ title }}
      </h2>
      <p
        class="text-2xl md:text-3xl mb-2 lg:mb-9 leading-[1.1] capitalize mt-7 content"
        v-motion-slide-visible-left
      >
        <slot />
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  title: {
    type: String,
    required: true,
  },
});
</script>
