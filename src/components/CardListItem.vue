<template>
  <div class="flex flex-col gap-4">
    <CartItem/>
    <CartItem/>
    <CartItem/>
    <CartItem/>
    <!-- <CartItem/> -->
    </div>
</template>
<script setup>
import CartItem from '@/components/CartItem.vue'

function onClickAdd() {
  alert('Add')
}
</script>
<style></style>
