<script setup>
import { ref } from "vue";
const openPopup = () => {
  alert('confirm')
}
</script>

<template>
<h2>press to confirm</h2>
  <button @click="openPopup">click here</button>
</template>

<style></style>
