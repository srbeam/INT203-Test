<script setup>
const count = 1
</script>

<template>
  <p> Counter: <b v-show="count > 2"> {{ count }} </b></p>
  <p> Counter: <b v-show="count < 2"> {{ count }} </b></p>
</template>

<style></style>





