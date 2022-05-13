<script setup>
import { ref } from 'vue'
const searchTrack = ref()
const shipments = ref([
  {id:1,trackingNum:'11111TH', sender:'Somsri',receiver:'Makky', status: 'Delivered'},
  {id:2,trackingNum:'22222TH', sender:'Samorn',receiver:'Maysa', status: 'In transit'},
  {id:3,trackingNum:'33333TH', sender:'Baibua',receiver:'Guitar', status: 'In transit'},
  {id:4,trackingNum:'44444TH', sender:'Arnon',receiver:'Pookko', status: 'Picked up'},
  {id:5,trackingNum:'443334TH', sender:'Saengsi',receiver:'Wichai', status: 'Picked up'}
])

const filterShipments = ref([])
const textDisplay = ref('')
const warningStyle = {
  color: 'darkred',
  fontSize: '18px'
}

const search = (searchTrack) => { 
  if (!searchTrack) filterShipments.value = [] , textDisplay.value = 'noSearch'
  else {
    filterShipments.value =  shipments.value.filter((shipment) => shipment.trackingNum.toLowerCase() == searchTrack.toLowerCase())
    textDisplay.value = 'haveShipment'
      if (filterShipments.value.length == 0) textDisplay.value = 'wrongTrack'
  }
  console.log(filterShipments.value)
  console.log(textDisplay.value)
}

</script>

<template>
<div>
  <h2>ติดตามสถานะพัสดุ</h2>
  <p>กรอกหมายเลขพัสดุเพื่อค้นหาข้อมูล</p>
  <input type='text' placeholder='ex.9999999TH' v-model="searchTrack">
  <button @click="search(searchTrack)">search</button>
  <br>
  <br>
  <table v-show="filterShipments.length > 0" align="center">
    <tr>
      <th> Tracking No.</th>
      <th> Sender</th>
      <th> Receiver</th>
      <th> Status</th>
    </tr>
    <tr v-for="(shipment,index) in filterShipments" :key="index" >
      <td> {{ shipment.trackingNum }} </td>
      <td> {{ shipment.sender }}</td>
      <td> {{ shipment.receiver }}</td>
      <td> {{ shipment.status }}</td>
    </tr>
  </table>
  <div>
  <p :style="warningStyle" v-if="textDisplay=='noSearch'"> ----- กรุณาใส่หมายเลขพัสดุ -----</p>
  <p :style="warningStyle" v-else-if="textDisplay=='wrongTrack'"> ----- ไม่พบข้อมูลการค้นหา -----</p>
  </div>
  </div>
</template>

<style>
  h2{
  color:#24305e;
  }
  p{
   color:#34495e;
  }
#app {
  font-family: 'Kanit', sans-serif;
  margin-left: 60px;
   text-align: center;
   background-color: #e9e9e9 ;
   margin-right: 60px ;
   padding-top: 10px;
   padding-bottom: 10px;
}
table {
  text-align: center;
}

th,td {
  text-align: center;
  padding-right: 15px;
}
td {
  text-align: center;
}
button{
  background-color: #F8E9A1;
  
}
</style>
