<template>
  <div class="flex flex-wrap gap-4">
    <Card v-for="(item, index) of items">
      <template #header>
        <img alt="user header" :src="item.image" />
      </template>
      <template #title>{{ item.title }}</template>
      <template #content>
        <p class="m-0">
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
import { ref } from 'vue'

const items = ref([
  {
    image: 'https://picsum.photos/400/200?random=1',
    title: 'First Post',
    description: 'This is the description of the first post.',
    date: '2025-09-03',
  },
  {
    image: 'https://picsum.photos/400/200?random=2',
    title: 'Second Post',
    description: 'This is the description of the second post.',
    date: '2025-09-02',
  },
  {
    image: 'https://picsum.photos/400/200?random=3',
    title: 'Third Post',
    description: 'This is the description of the third post.',
    date: '2025-09-01',
  },
])
</script>
