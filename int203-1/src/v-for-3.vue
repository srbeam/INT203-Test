<script setup>
const students = {
  id: 63130500116,
  name: 'Sarisa Phulakorn',
  group: 'B'
}
</script>

<template>
  <ul>
    <li v-for="(propValue, propKey) in students" >
      # {{propKey}}:
      {{propValue}}
      </li>
  </ul>
</template>

<style></style>
