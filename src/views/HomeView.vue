<template>
  <div class="flex flex-wrap gap-4">
    <Card v-for="(item, index) of items" class="flex-1 min-w-[calc(20%-1rem)] p-2">
      <template #header>
        <img alt="user header" :src="item.image" class="m-auto" />
      </template>
      <template #title v-if="item.title">{{ item.title }}</template>
      <template #content v-if="item.description">
        <p>
          {{ item.description }}
        </p>
      </template>
      <template #footer v-if="item.date">
        <span>{{ item.date }}</span>
      </template>
    </Card>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const items = ref(null)

onMounted(async () => {
  const data = await fetch('data.json').then((response) => response.json())
  items.value = await data['works']
})
</script>
