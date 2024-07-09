<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'

const items = ref([])

onMounted(async () => {
  try {
    const {data} = await axios.get('https://604781a0efa572c1.mokky.dev/items')
    items.value = data
  } catch (e) {
    console.log(e)
  }
})
</script>

<template>
  <!-- <Drawer /> -->
  <div class="w-4/5 m-auto bg-white rounded-xl shadow-xl my-14">
    <Header />
    <CardList :items="items" />
  </div>
</template>

<style scoped></style>
