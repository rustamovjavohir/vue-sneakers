<script setup>
import Header from '@/components/Header.vue'
import Drawer from '@/components/Drawer.vue'
import CardList from '@/components/CardList.vue'
</script>

<template>
  <!-- <Drawer /> -->
  <div class="bg-white w-4/5 m-auto rounded-2xl shadow-xl mt-14">
    <Header />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-4">Все красовки</h2>
        <div class="flex gap-4">
          <select class="py-2 px-3 border rounded-md outline-none">
            <option value="1">По названию</option>
            <option value="2">По цене(дешевые)</option>
            <option value="3">По цене(дорогие)</option>
          </select>
          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="Search icon" />
            <input
              class="border rounded-md py-2 pl-11 pr-4 outline-none focus:border-gray-500"
              type="text"
              placeholder="Поикс....."
            />
          </div>
        </div>
      </div>
      <CardList class="mt-4" />
    </div>
  </div>
</template>

<style scoped></style>
