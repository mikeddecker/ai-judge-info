<script setup>
import { computed, onMounted, ref } from 'vue'

const about = ref(null)
const name = computed(() => about.value ? about.value['name'] : 'me')
const info = computed(() => about.value ? about.value['info'] : '')
const phone = computed(() => about.value ? about.value['phone'] : '')
const email = computed(() => about.value ? about.value['email'] : '')

const placeItems = 'center'

onMounted(async () => {
  about.value = await fetch('data.json').then((response) =>
    response.json().then((value) => value['about']),
  )
})
</script>

<template>
  <div class="container w-250 place-items-center flex flex-wrap">
    <h1 class="">{{ name }}</h1>
    <img :src="about ? about['picture'] : 'me'" class="w-200"></img>
    <p>{{ info }}</p>
    <p>{{ email }}</p>
    <p>{{ phone }}</p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .container * {
    width: 100%;
  }
}
</style>

