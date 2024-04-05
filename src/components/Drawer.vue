<template>
  <div class="fixed top-0 left-0 h-full w-3/5 md:w-3/4 lg:w-4/5 bg-black z-10 opacity-70"></div>
  <div class="fixed top-0 right-0 h-full w-2/5 md:w-1/4 lg:w-1/5 bg-white z-20 p-8">
    <DrawerHader />

    <CardListItem />

    <div class="flex flex-col gap-4 my-4">
      <div class="flex gap-2">
        <span>Итого:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>12999$</b>
      </div>
      <div class="flex gap-2">
        <span>Налог 5%:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>5$</b>
      </div>
      <button
        class="bg-lime-500 w-full rounded-xl py-3 mt-6 text-white transition hover:bg-lime-600 hover:-translate-y-1 active:bg-lime-700 disabled:bg-slate-300"
      >
        Оформить заказ
      </button>
    </div>
  </div>
</template>
<script setup>
import DrawerHader from '@/components/DrawerHader.vue'
import CardListItem from '@/components/CardListItem.vue'
</script>
<style></style>
