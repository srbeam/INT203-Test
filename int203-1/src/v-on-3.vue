<script setup>
import { ref } from "vue";

const item = ref()
const submit = () => {
  alert('edit success');
}
</script>

<template>
<h2>Click submit to confirm</h2>
<form v-on:submit="submit">
  <input>
  <button>submit</button>
  </form>
</template>

<style></style>