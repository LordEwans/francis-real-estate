<script lang="ts" setup></script>

<template>
  <div
    class="lg:flex lg:justify-center lg:items-center min-w-full bg-gradient-to-tr"
    id="learn-more"
  >
    <div class="lg:container">
      <div class="hero w-full min-h-[50vh]">
        <div class="text-center flex justify-center items-center">
          <div class="w-[96%] md:max-w-2xl lg:max-w-6xl align-top">
            <div class="w-full mb-12 md:mb-16">
              <div class="min-h-screen flex items-center">
                <div>
                  <h2
                    class="capitalize text-3xl md:text-6xl leading-[1.1] font-extrabold"
                    v-motion-slide-visible-right
                  >
                    Get exclusive access to premium properties
                  </h2>
                  <p
                    class="text-2xl md:text-3xl mb-2 lg:mb-9 leading-[1.1] capitalize mt-7 content"
                    v-motion-slide-visible-right
                  >
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Aliquid saepe et voluptatibus ex! Necessitatibus ipsum rerum
                    pariatur. Tempore ipsam earum similique necessitatibus. Qui
                    numquam quisquam eaque alias natus quos iste?
                  </p>
                </div>
              </div>
              <div class="min-h-[50vh] flex items-center">
                <div>
                  <h2
                    class="capitalize text-3xl md:text-6xl leading-[1.1] font-extrabold"
                    v-motion-slide-visible-left
                  >
                    Understand the current state of the market
                  </h2>
                  <p
                    class="text-2xl md:text-3xl mb-2 lg:mb-9 leading-[1.1] capitalize mt-7 content"
                    v-motion-slide-visible-left
                  >
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Facilis aperiam facere molestias est blanditiis neque natus.
                    Repudiandae tempore praesentium velit alias iure nostrum ab
                    expedita, ut amet deleniti fuga itaque.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.content {
  font-family: "Sever";
}
</style>
