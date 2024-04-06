<script setup>
import { onMounted } from 'vue'
import axios from 'axios'

import Header from '@/components/Header.vue'
import Drawer from '@/components/Drawer.vue'
import CardList from '@/components/CardList.vue'

onMounted(async () => {
  console.log('App mounted!')
  const url_ = 'https://c248f9b7213dc741.mokky.dev/items'
  // fetch(url_)
  //   .then(response => response.json())
  //   .then(data => console.log(data))
  //   .catch(error => console.error(error))

  try {
    const data = await axios.get(url_)
    console.log(data)
  } catch (error) {
    console.error(error)
  }
  // axios
  //   .get(url_)
  //   .then((response) => console.log(response.data))
  //   .catch((error) => console.error(error))
})
const items = [
  {
    id: 1,
    title: 'Мужские Кроссовки Nike Blazer Mid Suede',
    price: 12999,
    imageUrl: '/sneakers/sneakers-1.jpg'
  },
  {
    id: 2,
    title: 'Мужские Кроссовки Nike Air Max 270',
    price: 15600,
    imageUrl: '/sneakers/sneakers-2.jpg'
  },
  {
    id: 3,
    title: 'Мужские Кроссовки Nike Blazer Mid Suede',
    price: 8499,
    imageUrl: '/sneakers/sneakers-3.jpg'
  },
  {
    id: 4,
    title: 'Кроссовки Puma X Aka Boku Future Rider',
    price: 7800,
    imageUrl: '/sneakers/sneakers-4.jpg'
  },
  {
    id: 5,
    title: 'Кроссовки Future Rider',
    price: 9550,
    imageUrl: '/sneakers/sneakers-5.jpg'
  },
  {
    id: 6,
    title: 'Кроссовки Black Edition',
    price: 16999,
    imageUrl: '/sneakers/sneakers-6.jpg'
  },
  {
    id: 7,
    title: 'Кроссовки Orange Boomb Edition',
    price: 7499,
    imageUrl: '/sneakers/sneakers-7.jpg'
  },
  {
    id: 8,
    title: 'Кроссовки Nike Air Max 270',
    price: 15600,
    imageUrl: '/sneakers/sneakers-8.jpg'
  },
  {
    id: 9,
    title: 'Кроссовки Nike Air Force 1',
    price: 5900,
    imageUrl: '/sneakers/sneakers-9.jpg'
  },
  {
    id: 10,
    title: 'Кроссовки Adidas Ultraboost',
    price: 11500,
    imageUrl: '/sneakers/sneakers-10.jpg'
  },
  {
    id: 11,
    title: 'Кроссовки Puma Clyde All-Pro',
    price: 7600,
    imageUrl: '/sneakers/sneakers-11.jpg'
  },
  {
    id: 12,
    title: 'Кроссовки Converse Chuck Taylor All-Star',
    price: 13000,
    imageUrl: '/sneakers/sneakers-12.jpg'
  }
]
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
      <CardList class="mt-10" :items="items" />
    </div>
  </div>
</template>

<style scoped></style>
