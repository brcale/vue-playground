<!-- Counter with Pinia store -->

<script setup>
import { useCounterStore } from '../stores/counter'
const store = useCounterStore()
</script>

<template>
  <h1>Counter with pinia</h1>
  <h2>Total Clicks: {{ store.totalClicks }}</h2>
  <div class="card">
    <button type="button" @click="store.increment('a')">
      Option A clicked {{ store.options['a'] }} times
    </button>
    <button type="button" @click="store.increment('b')">
      Option B clicked {{ store.options['b'] }} times
    </button>
    <button type="button" @click="store.increment('c')">
      Option C clicked {{ store.options['c'] }} times
    </button>
  </div>
</template>
