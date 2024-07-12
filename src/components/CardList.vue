<script setup>
import Card from './Card.vue'

defineProps({
  items: Array
})

</script>

<template>
  <div class="grid grid-cols-4 gap-5 p-10">
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
</template>
