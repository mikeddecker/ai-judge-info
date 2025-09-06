<script setup>
import { computed, onMounted, ref } from 'vue'

const about = ref(null)
const name = computed(() => about.value ? about.value['name'] : 'me')
const info = computed(() => about.value ? about.value['info'] : '')
const phone = computed(() => about.value ? about.value['phone'] : '')
const email = computed(() => about.value ? about.value['email'] : '')

onMounted(async () => {
  about.value = await fetch('data.json').then((response) =>
    response.json().then((value) => value['about']),
  )
})
</script>

<template>
  <div class="w-250 place-items-center">
    <h1>About {{ name }}</h1>
    <img :src="about ? about['picture'] : 'me'" class="w-40"></img>
    <p>{{ info }}</p>
    <p>{{ email }}</p>
    <p>{{ phone }}</p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
}
</style>

