<script setup>
import { RouterLink, RouterView } from 'vue-router'
const fadingHeader = 'bg-gradient-to-b from-emerald-600/70 to-emerald-600/0'
</script>

<template>
  <header class="w-full py-8 flex" :class="fadingHeader">
    <nav class="my-auto mx-auto flex gap-4 items-center">
      <RouterLink class="text-xl font-medium" to="/">Home</RouterLink>
      <img class="w-20 h-auto" src="/src/assets/logo.svg"></img>
      <RouterLink class="text-xl font-medium" to="/about">About</RouterLink>
    </nav>
  </header>
  <main class="pt-4 px-8">
    <RouterView />
  </main>
</template>

<style scoped>
@media (min-width: 1024px) {
}
</style>

