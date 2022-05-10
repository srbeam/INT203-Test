<script setup>
import { ref } from 'vue'
console.clear()
const width = ref(0)
const length = ref(0)
const area = ref(0)
function computeArea() {
  area.value = width.value * length.value
}
</script>

<template>
  <p>Width: {{ width }}</p>
  <button @click="++width">Add </button>
  <button @click="--width">reduce</button>
  <p>Height: {{ length }}</p>
  <button @click="++length">Add </button>
  <button @click="--length">reduce</button>
<br>
<br>
  <button @click="computeArea">Compute</button>
  <p>Result Area: {{ area }}</p>
</template>

<style></style>
