<script lang="ts" setup>
import { useScroll } from "@vueuse/core";
const sec = ref<HTMLElement | null>(null);
const navStyle = ref("");
const { x, y, isScrolling, arrivedState, directions } = useScroll(sec);

if (arrivedState.bottom) {
  //navStyle.value = "backdrop-filter: blur(9px);";
  console.log("Yes");
} else {
  //navStyle.value = "backdrop-filter: blur(0px);";
  console.log("No");
}
</script>

<template>
  <Head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital,wght@0,700;1,400&display=swap"
      rel="stylesheet"
    />
  </Head>
  <title>Francis Estates - Elegance Meets Competence</title>
  <Navigation :style="navStyle" />
  <div class="lg:flex lg:justify-center lg:items-center min-h-screen">
    <div class="lg:container">
      <div class="hero w-full min-h-screen">
        <div class="hero-content max-w-full w-full">
          <div class="text-center flex justify-center">
            <div class="md:max-w-2xl lg:max-w-6xl align-top">
              <div class="w-full mb-12 md:mb-16">
                <h1
                  class="text-2xl mb-2 lg:mb-9 md:text-[clamp(2rem,4vw,4.2rem)] leading-[1.1] capitalize"
                  v-motion-slide-visible-bottom
                >
                  Cheap and Affordable Properties
                </h1>
                <h2
                  class="capitalize text-3xl md:text-[clamp(2.7rem,4vw,4rem)] leading-[1.1] font-extrabold"
                  v-motion-slide-visible-bottom
                >
                  Find the best value for your money
                </h2>
              </div>
              <div class="" v-motion-pop-visible>
                <button class="btn mx-6 bg-gray-700 border-gray-700 text-white">
                  Manage Estates
                </button>
                <a
                  href="#learn-more"
                  class="btn btn-ghost text-white hover:bg-transparent hover:underline"
                  >Learn More</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div
    class="bg-gray-800 bg-opacity-80 w-full"
    style="backdrop-filter: blur(9px)"
  >
    <Content />
    <Contact />
    <Footer />
  </div>
</template>

<style></style>
