<script setup>
import { onMounted, ref, reactive, watch, provide } from 'vue'
import axios from 'axios'

import Header from '@/components/Header.vue'
import Drawer from '@/components/Drawer.vue'
import CardList from '@/components/CardList.vue'

const items = ref([]) // {'value': []}

const filters = reactive({
  sortBy: '',
  searchQuery: ''
})

const addToFavourite = async (item) => {
  item.isFavourite = true

  console.log(item)
}

async function fetchFavourites() {
  const url_ = 'https://c248f9b7213dc741.mokky.dev/favourites'
  try {
    const { data: favourites } = await axios.get(url_)
    console.log(favourites)

    items.value = items.value.map((item) => {
      const favourite = favourites.find((favourite) => favourite.parentId === item.id)
      if (!favourite) {
        return item
      }
      return {
        ...item,
        isFavourite: true,
        favouriteId: favourite.id
      }
    })
  } catch (error) {
    console.error(error)
  }
}

async function getItems() {
  const url_ = 'https://c248f9b7213dc741.mokky.dev/items'
  const params = {
    // sortBy: filters.sortBy
  }
  if (filters.searchQuery) {
    params.title = `*${filters.searchQuery}*`
  }
  if (filters.sortBy) {
    params.sortBy = filters.sortBy
  }
  try {
    const { data } = await axios.get(url_, { params })
    items.value = data
  } catch (error) {
    console.error(error)
  }
}

onMounted(async () => {
  await getItems()
  await fetchFavourites()
})

watch(filters, getItems)

provide('addToFavourite', addToFavourite)

function onChangeSelect(e) {
  if (e.target.value === 'title') {
    filters.sortBy = 'title'
  } else if (e.target.value === 'price') {
    filters.sortBy = 'price'
  } else if (e.target.value === '-price') {
    filters.sortBy = '-price'
  } else {
    filters.sortBy = ''
  }
}

function onChangeSearch(e) {
  filters.searchQuery = e.target.value
  console.log(filters.searchQuery)
}
</script>

<template>
  <!-- <Drawer /> -->
  <div class="bg-white w-4/5 m-auto rounded-2xl shadow-xl mt-14">
    <Header />
    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-4">Все красовки</h2>
        <div class="flex gap-4">
          <select @change="onChangeSelect" class="py-2 px-3 border rounded-md outline-none">
            <option value="" selected>Выберите один раз</option>
            <option value="title">По названию</option>
            <option value="price">По цене(дешевые)</option>
            <option value="-price">По цене(дорогие)</option>
          </select>
          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="Search icon" />
            <input
              @keyup="onChangeSearch"
              class="border rounded-md py-2 pl-11 pr-4 outline-none focus:border-gray-500"
              type="text"
              placeholder="Поикс....."
            />
          </div>
        </div>
      </div>
      <CardList class="mt-10" :items="items" />
    </div>
  </div>
</template>

<style scoped></style>
