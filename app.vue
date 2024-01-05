<template>
  <video autoplay muted loop id="bg-video">
    <source src="assets/videos/bg-vid.mp4" type="video/mp4" />
  </video>
  <div class="bg-mask bg-black bg-opacity-20" id="bg-video"></div>
  <div class="body animate-border">
    <NuxtPage />
    <Contact />
    <WIP />
  </div>
</template>

<style>
#bg-video {
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  z-index: -1;
}

.bg-mask {
  -webkit-mask-image: linear-gradient(black, black);
  mask-image: linear-gradient(black, black);
}
</style>
