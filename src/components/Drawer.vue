<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black opacity-70 z-10"></div>
  <div class="flex flex-col bg-white w-96 h-full fixed right-0 top-0 z-20 p-8 pr-3">
    <DrawerHead />
    <CartItemList />
    <div class="flex flex-col gap-4 mb-6">
      <div class="flex gap-2">
        <span>Итого:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>12900 Р</b>
      </div>
      <div class="flex gap-2">
        <span>Налог 5%:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>12900 Р</b>
      </div>
    </div>
    <button class="bg-lime-500 w-full rounded-xl py-3 transition disabled:bg-slate-400 hover:bg-lime-600">
      Оформить заказ
    </button>
  </div>
</template>
