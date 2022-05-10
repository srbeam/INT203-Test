<script setup>
const amount = 500
</script>

<template>
  <p>Amount: {{ amount }}</p>
  <p v-if="amount <= 500">Fee: {{ amount * 0.07 }}</p>
  <p v-else-if="amount > 500">Fee: {{ amount * 0.05 }}</p>
  <p v-else>Fee: {{ amount * 0.01 }}</p>
</template>

<style></style>

