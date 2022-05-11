<script setup>
import { computed, ref } from "vue";

const bgColor = ref('#ff0000')
const textSize = ref('14px')
const bgColorChange = ref('')
const textSizeChange = ref('')

const italic = ref('')
const underline = ref('')
const bold = ref('')
const style = ref([])

const change = () => {
  bgColorChange.value = bgColor.value
  textSizeChange.value = textSize.value
  italic.value = style.value.find(style => style == 'italic')
  underline.value = style.value.find(style => style == 'underline')
  bold.value = style.value.find(style => style == 'bold')
}
const reset = () => {
  bgColor.value = '#ff0000' , textSize.value = '14px',
  bgColorChange.value = '' , textSizeChange.value = '',
  italic.value = '' ,underline.value = '' , bold.value = '' , style.value = []
}
</script>
 
<template>
  <div>
    <select v-model="bgColor">
      <option value="#ff0000">red</option>
      <option value="#4169E1">Blue</option>
      <option value="#A020F0">Purple</option>
      <option value="#FFC0CB">Pink</option>
      <option value="#2E8B57">Green</option>
      <option value="#8B4513">Brown</option>
    </select>

    <input type="color" :value="`${bgColor}`" />

    <select v-model="textSize">
      <option value="14px">14px</option>
      <option value="16px">16px</option>
      <option value="20px">20px</option>
      <option value="24px">24px</option>
      <option value="28px">28px</option>
      <option value="32px">32px</option>
    </select>

    <input type="checkbox" value="italic" v-model="style" /> Italic
    <input type="checkbox" value="underline" v-model="style" /> underline
    <input type="checkbox" value="bold" v-model="style" /> Bold

    <div>
      <button @click="change">Change</button>
      <button @click="reset">Reset</button>
    </div>

    <textarea :style="{
        'background-color': bgColorChange,
        'font-size': textSizeChange,
        'font-style': italic,
        'text-decoration': underline,
        'font-weight': bold,
      }"> Hello World </textarea>
  </div>
</template>
 
<style></style>
