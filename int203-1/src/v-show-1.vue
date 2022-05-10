<script setup>
const surname = 'sarisa'
</script>

<template>
  <p> Surname: {{surname }}</p>
  <p v-show="!surname" style="color: red" > Please enter your surname!</p> 
  <p> Lastname: {{lastname }}</p>
  <p v-show="!lastname" style="color: red" > Please enter your lastname!</p>

<!-- ไม่ใส่ lastname จะเเสดง true ข้อความจะปรากฎ -->
</template>

<style></style>





