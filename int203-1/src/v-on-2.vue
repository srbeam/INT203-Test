<script setup>
import { ref } from 'vue'
const textSize = ref('')
const changeSize = ref('')
const change = () => {
  changeSize.value = textSize.value
}
</script>

<template>
<select size="1"  v-model="textSize">
  <option value="20px">small</option>
  <option value="40px">medium</option>
  <option value="60px">large</option>
</select>
  <button @click="change">Change Size</button>


<p class="size">
  Thank you for your attention!
</p>

</template>

<style>
.size{
  font-size: v-bind(changeSize);
  }
</style>
