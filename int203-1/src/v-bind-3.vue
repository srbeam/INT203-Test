<script setup>
const textColor = "orange";
const bgColor = "red";
const textSize = "25px";
const font = "Arial";
</script>
 
<template>
<p v-bind:style="{'font-family':font ,'font-size':size, backgroundColor:bgColor}" >
   Today is Monday
</p>
</template>
 
<style>

</style>





