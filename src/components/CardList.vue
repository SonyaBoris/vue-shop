<script setup>
import Card from './Card.vue'

defineProps({
  items: Array
})
</script>

<template>
  <div class="p-10">
    <div class="flex justify-between items-center mb-10">
      <h2 class="text-3xl font-bold mb-8">Все кросовки</h2>
      <div class="flex gap-4">
        <select class="py-2 px-3 border rounded-md outline-none">
          <option>По названию</option>
          <option>По цене (дешевые)</option>
          <option>По цене (дорогие)</option>
        </select>
        <div class="relative">
          <img class="absolute left-4 top-4" src="/search.svg" alt="" />
          <input
            class="border rounded-md pl-11 py-3 outline-none"
            type="text"
            placeholder="Поиск..."
          />
        </div>
      </div>
    </div>

    <div class="grid grid-cols-4 gap-5">
      <Card
        v-for="item in items"
        :key="item.id"
        :imageUrl="item.imageUrl"
        :title="item.title"
        :price="item.price"
        :isAdded="true"
        :isFavorite="true"
        :onClickAdd="onClickAdd"
      />
    </div>
  </div>
</template>
