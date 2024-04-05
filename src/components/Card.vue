<template>
  <div>
    <div
      class="relative bg-white border-slate-100 border-2 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
    >
      <img
        :src="isFavourite ? '/like-2.svg' : '/like-1.svg'"
        alt="Like 1"
        class="absolute top-8 left-8"
        @click="onClickFavourite"
      />
      <img :src="imageUrl" alt="" />
      <p class="mt-2">{{ title }}</p>
      <div class="flex justify-between mt-5">
        <div class="flex flex-col">
          <span class="text-slate-400">Цена:</span>
          <b>{{ price }} som.</b>
        </div>
        <img @click="onClickAdd" :src="isAdded ? '/checked.svg' : '/plus.svg'" alt="Plus" />
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'

defineProps({
  imageUrl: String,
  title: {
    type: String,
    required: true
  },
  price: Number,
  isFavourite: {
    type: Boolean,
    default: false
  },
  isAdded: {
    type: Boolean,
    default: false
  },
  onClickAdd: Function,
  onClickFavourite: Function
})
</script>
<style></style>
