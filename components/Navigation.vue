<script lang="ts" setup>
</script>

<template>
  <div class="drawer drawer-end">
    <input id="my-drawer-4" type="checkbox" class="drawer-toggle" />
    <div class="drawer-content">
      <div class="flex justify-center">
        <header
          class="navbar py-[.2em] will-change-transform top-0 w-[96%] border-0"
        >
          <div class="navbar-start ml-2 md:ml-6 block text-base">
            <a
              href="/"
              class="btn bg-transparent hover:bg-transparent min-h-0 h-0 p-0 border-transparent hover:border-transparent text-base text-white"
            >
              Francis Estates
            </a>
          </div>
          <nav class="lg:flex justify-self-center hidden navbar-end">
            <ul class="flex">
              <li class="partials">
                <a href="#estates" class="partials">Estates</a>
              </li>
              <li class="partials">
                <a href="#ecosystem" class="partials">Ecosystem</a>
              </li>
              <li class="partials">
                <a href="#contact" class="partials">Contact</a>
              </li>
            </ul>
            <!-- <button>
        <img src="assets/img/animated/day.svg" alt="Default" />
      </button> -->
          </nav>
          <div class="max-lg:navbar-end">
            <label
              for="my-drawer-4"
              class="drawer-button btn btn-ghost text-s btn-primary lg:hidden"
              style="--tw-bg-opacity: 0"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 fill-[var(--border-color)]"
                viewBox="0 0 24 24"
                stroke="white"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h8m-8 6h16"
                />
              </svg>
            </label>
          </div>
        </header>
      </div>
    </div>

    <div class="drawer-side z-10 lg:hidden">
      <label
        for="my-drawer-4"
        aria-label="close sidebar"
        class="drawer-overlay"
      />
      <ul
        class="menu p-4 w-[70%] md:w-80 min-h-full bg-slate-950 text-base-content"
      >
        <li class="partials">
          <a href="#features" class="partials">Features</a>
        </li>
        <li class="partials">
          <a href="#ecosystem" class="partials">Ecosystem</a>
        </li>
        <li class="partials">
          <a href="#trading" class="partials">Trading</a>
        </li>
        <div>
          <button
            class="btn btn-outline text-xs mx-6 btn-primary mt-9"
          >
            Connect Wallet
          </button>
        </div>
      </ul>
    </div>
  </div>
</template>

<style>
li.partials {
  @apply inline mx-5 font-semibold;
}
.partials {
  @apply inline-block uppercase font-bold text-xs text-white;
}
.btn {
  @apply rounded-2xl;
}
header {
  @apply mt-4 w-[96%] border-[var(--border-color)] border-opacity-60;
}
.drawer-side {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.drawer-side::-webkit-scrollbar {
  display: none;
}
</style>
