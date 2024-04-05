<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      imageUrl="/sneakers/sneakers-1.jpg"
      title="Some text"
      :price="1250"
      :isAdded="true"
      :onClickAdd="onClickAdd"
    />
    <Card imageUrl="/sneakers/sneakers-1.jpg" title="Some text" :price="1250" :isFavourite="true" />
    <Card imageUrl="/sneakers/sneakers-1.jpg" title="Some text" :price="1250" />
    <Card imageUrl="/sneakers/sneakers-1.jpg" title="Some text" :price="1250" />
    <Card imageUrl="/sneakers/sneakers-1.jpg" title="Some text" :price="1250" />
    <Card imageUrl="/sneakers/sneakers-1.jpg" title="Some text" :price="1250" />
  </div>
</template>
<script setup>
import Card from '@/components/Card.vue'

function onClickAdd() {
  alert('Add')
}
</script>
<style></style>
