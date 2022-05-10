<script setup>
const animals = ['cat', 'dog', 'hamster', 'cow']
</script>

<template>
  <ul>
    <li v-for="(animal, index) in animals" :key="index">{{index}} - {{ animal }}</li>
  </ul>
</template>

<style></style>
