<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :imageUrl="item.imageUrl"
      :title="item.title"
      :price="item.price"
      :onClickAdd="onClickAdd"
      :isFavourite="item.isFavourite"
      :onClickFavourite="() => addToFavourite(item)"
    />
  </div>
</template>
<script setup>
import Card from '@/components/Card.vue'
import { inject } from 'vue'

const addToFavourite = inject('addToFavourite')



function onClickAdd() {
  alert('Add')
}

defineProps({
  items: Array
})

// console.log(items)
</script>
<style></style>

i
