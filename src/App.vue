<script setup>
import { onMounted, ref, watch, reactive } from 'vue'
import axios from 'axios'
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'

const items = ref([])

const filters = reactive({
  sortBy: 'title',
 searchQuery: ''
})

const onChangeSelect = (e) => {
  filters.sortBy = e.target.value
}

const onChangeInput = (e) =>{
  filters.searchQuery = e.target.value
}
const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy
    }
    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    const { data } = await axios.get('https://604781a0efa572c1.mokky.dev/items', {
      params
    })
    items.value = data
  } catch (e) {
    console.log(e)
  }
}
onMounted(fetchItems)

watch(filters, fetchItems)
</script>

<template>
  <!-- <Drawer /> -->

  <div class="w-4/5 m-auto bg-white rounded-xl shadow-xl">
    <Header />
    <div class="p-10 flex justify-between items-center">
      <h2 class="text-3xl font-bold mb-8">Все кросовки</h2>
      <div class="flex gap-4">
        <select @change="onChangeSelect" class="py-2 px-3 border rounded-md outline-none">
          <option value="name">По названию</option>
          <option value="price">По цене (дешевые)</option>
          <option value="-price">По цене (дорогие)</option>
        </select>
        <div class="relative">
          <img class="absolute left-4 top-4" src="/search.svg" alt="" />
          <input
            @input="onChangeInput"
            class="border rounded-md pl-11 py-3 outline-none"
            type="text"
            placeholder="Поиск..."
          />
        </div>
      </div>
    </div>
    <CardList :items="items" />
  </div>
</template>

<style scoped></style>
