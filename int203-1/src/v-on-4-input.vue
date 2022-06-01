<script setup>
import { ref } from "vue";

const item = ref()

</script>

<template>
<h2>Today is {{item}}</h2>

  <input type="text" @input=" item=$event.target.value">
  
  
</template>

<style></style>
