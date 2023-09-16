<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h2>Hello there!</h2>
  <h1>{{msg}}</h1>
</template>

<style scoped>

</style>
