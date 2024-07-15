<script setup>
import { ref } from 'vue'

const count = ref(0)
const data = ref('')
const isLoading = ref(false)

const inc = () => {
  count.value++
}
const dec = () => {
  count.value--
}

async function fetchData() {
  try {
    isLoading.value = true
    const response = await fetch('https://api.coindesk.com/v1/bpi/currentprice.json')
    const actualData = await response.json()
    data.value = actualData
  } catch (e) {
    console.error('There was an error: ', e)
  } finally {
    isLoading.value = false
  }
}
</script>

<template>
  <p>{{ count }}</p>
  <button @click="inc">Increment</button>
  <button @click="dec">Decrement</button>
  <div>
    <button @click="fetchData">Fetch crypto data</button>
    <p v-if="!isLoading">{{ data }}</p>
    <p v-else>LOADING...</p>
  </div>
</template>
