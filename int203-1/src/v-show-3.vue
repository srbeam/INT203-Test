<script setup>
const drinks = 'juice'
</script>

<template>
  <p> What do you like to drink? : <b v-show="true"> {{ drinks }} </b></p>
  <p> What do you like to drink? : <b v-show="fault"> {{ drinks }} </b></p>
</template>

<style></style>





