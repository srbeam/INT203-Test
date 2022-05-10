<script setup>
import { computed, ref } from "vue"

const numbers = [1,2,3]

const bColor = ref('#ff0000')
const textSize = ref('16px')

const toReset = () => { colorChanged.value = '#ff0000' , textChanged.value ='16px' }
const toChange = () => {  colorChanged.value = bColor.value , textChanged.value=textSize.value}

const textChanged = ref('16px')
const colorChanged = ref('#ff0000')

</script>
 
<template>
<div>
  <select v-model="bColor">
      <option value="#ff0000"> red </option>
      <option value="#98fb98"> palegreen </option>
      <option value="#eee8aa"> palegoldenrod </option>
      <option value="#afeeee"> paleturquoise </option>
      <option value="#d87093"> palevioletred </option>
    </select>    
  
    <!-- <span> {{ bColor }}</span> -->

    <!-- <h1 :style="`color:${bColor}`"> Color </h1> -->

    <input type="color" :value="`${colorChanged}`"/>

    <select v-model="textSize">
      <option value="12px"> 12px </option>
      <option value="14px"> 14px </option>
      <option value="16px"> 16px </option>
      <option value="20px"> 20px </option>
      <option value="24px"> 24px </option>
      <option value="28px"> 28px </option>
      <option value="32px"> 32px </option>
    </select>

    <div> 
      <button @click="toChange"> Change </button> 
      <button @click="toReset"> Reset </button> 
    </div>    

    <br><br>
  <ul>
    <li v-for="(num,index) in numbers" :key="index" :style="`font-size:${textChanged}`"> 
      Hello {{ num }} 
    </li>
  </ul>

</div>
</template>
 
<style scoped>

</style>
