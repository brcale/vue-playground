<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div>
    <p>{{ msg }}</p>
  </div>
</template>
