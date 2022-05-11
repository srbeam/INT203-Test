<script setup>
const students = [
  {id:1, name:'Somsri', gpa: 3.5},
  {id:2, name:'Somchai', gpa: 3.1},
  {id:3, name:'Somsong', gpa: 2.7}
]

</script>

<template>
  <h2>ติดตามสถานะสิ่งของ</h2>
  <p>กรอกหมายเลขสิ่งของเพื่อค้นหาข้อมูล</p>
  <input type='text' placeholder='ex.9999999TH'>
  <button @click="search">search</button>
</template>

<style>
  h2 {
    /* margin-left: 60px; */
  }
  p{
   color:#34495e;
  }
#app {
  font-family: 'Kanit', sans-serif;
  margin-left: 60px;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
