<template>
  <header class="flex justify-between border-b border-slate-200 px-8 py-4">
    <div class="flex items-center gap-4">
      <img src="/logo.png" alt="Logo" class="w-10" />
      <div>
        <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
        <p class="text-slate-400">Магазин лучших кроссово</p>
      </div>
    </div>
    <div class="flex items-center gap-5">
      <ul>
        <li
          @click="() => emit('openDrawer')"
          class="flex items-center cursor-pointer gap-2 text-gray-500 hover:text-black"
        >
          <img src="/cart.svg" alt="Card logo" />
          <span>1205 рубл.</span>
        </li>
      </ul>
      <ul>
        <li class="flex items-center cursor-pointer gap-2 text-gray-500 hover:text-black">
          <img src="/heart.svg" alt="Favourite logo" />
          <span>Закладки</span>
        </li>
      </ul>
      <ul>
        <li class="flex items-center cursor-pointer gap-2 text-gray-500 hover:text-black">
          <img src="/profile.svg" alt="Profile logo" />
          <span>Профиль</span>
        </li>
      </ul>
    </div>
  </header>
</template>
<script setup>
const emit = defineEmits(['openDrawer'])
</script>
<style></style>
