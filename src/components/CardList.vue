<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
    v-for="item in items" :key="item.id"
      :imageUrl="item.imageUrl"
      :title="item.title"
      :price="item.price"
      :onClickAdd="onClickAdd"
    />
  </div>
</template>
<script setup>
import Card from '@/components/Card.vue'

function onClickAdd() {
  alert('Add')
}

defineProps({
  items: Array
})

// console.log(items)
</script>
<style></style>
