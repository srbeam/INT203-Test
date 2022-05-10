<script setup>
const numbers = ['one', 'two', 'three', 'four']
</script>

<template>
  <ul>
    <li v-for="number in numbers" >{{number}}</li>
  </ul>
</template>

<style></style>
