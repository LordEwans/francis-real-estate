<template>
  <div
    class="bg-[url('assets/image/pexels-expect-best-323780.jpg')] bg-no-repeat bg-center bg-cover min-h-[50vh] md:min-h-[75vh]"
  >
    <video
      src="assets/videos/Luxury Real Estate Drone Video • 4K Flights • DJI Phantom & Osmo.mp4"
      autoplay
      muted
      loop
      class="bg-video"
    ></video>
    <Navigation />
  </div>
</template>

<style>
.bg-video {
  @apply fixed right-0 bottom-0 min-w-full min-h-full -z-10 hidden;
}
</style>