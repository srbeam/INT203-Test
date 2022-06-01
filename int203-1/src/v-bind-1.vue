<script setup>
import {ref} from 'vue';

const headingStyle = "color: blue "
const paraStyle = "text-decoration: underline" 
const image = ref("./src/assets/logo.png")

</script>
 
<template>
<h1 :style ="headingStyle"> INT203 Client side </h1>
<p :style ="paraStyle"> Midterm </p>
<img :src="image"/>

</template>
 
<style>
</style>