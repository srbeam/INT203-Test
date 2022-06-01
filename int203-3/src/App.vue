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
  // search track
const search = (searchTrack) => { 
  if (!searchTrack) filterShipments.value = [] , textDisplay.value = 'noSearch'
  else {
    filterShipments.value =  shipments.value.filter((shipment) => shipment.trackingNum.toLowerCase() == searchTrack.toLowerCase())
    textDisplay.value = 'haveShipment'
      if (filterShipments.value.length == 0) textDisplay.value = 'wrongTrack'
  }
}

 // show all
const showAllTrack = ref()
const toShowAllTrack = () => {
  if(showAllTrack.value == true) showAllTrack.value = false
  else showAllTrack.value = true
}

  // add func
const showForm = ref()
const toShowForm = () => {
  if(showForm.value == true) showForm.value = false
  else showForm.value = true
}

const newShipment = ref({})
const newTrack = ref()
const newSender = ref()
const newReceiver = ref()
const newStatus = ref('Picked up')

const addNewShipment = () => {
  newShipment.value = {trackingNum:newTrack.value,sender:newSender.value,
  receiver:newReceiver.value,status:newStatus.value,id:shipments.value.length+1}
  shipments.value.push(newShipment.value)
  showForm.value = false
  newTrack.value = '',newSender.value = '',newReceiver.value = '',newStatus.value = 'Picked up'
}

// delete func
const deleteShipment = (index) => { shipments.value.splice(index, 1) }

// edit func
const shipmentId = ref()
const showEditShipment = ref()
const toShowEditShipment = (index) => {
  if(showEditShipment.value == true) showEditShipment.value = false
  else showEditShipment.value = true

  shipmentId.value = index+1
  console.log(shipmentId.value)

  trackNum.value = shipments.value[index].trackingNum
  console.log (trackNum.value)
  
}

const senderUpdate = ref() 
const receiverUpdate = ref() 
const statusUpdate = ref()
const trackNum = ref()
const editShipment = () =>{
  shipments.value = shipments.value.map(shipment =>
  shipment.id === shipmentId.value
    ? { ...shipment, sender:senderUpdate.value ,receiver: receiverUpdate.value, status: statusUpdate.value}
    : shipment
  );
  senderUpdate.value = '', receiverUpdate.value = '', statusUpdate.value = 'Picked up'
}


</script>

<template>
<div>
  <h2>ติดตามสถานะพัสดุ</h2>
  <p>กรอกหมายเลขพัสดุเพื่อค้นหาข้อมูล</p>
  <input type='text' placeholder='ex.9999999TH' v-model="searchTrack">
  <button @click="search(searchTrack)">search</button>

  <!-- list all -->
  <button @click="toShowAllTrack">all tracking</button>
  <div v-show="showAllTrack"> <br>
    <table  align="center">
    <tr>
      <th> Tracking No.</th>
      <th> Sender</th>
      <th> Receiver</th>
      <th> Status</th>
    </tr>
    <tr v-for="(shipment,index) in shipments" :key="index" >
      <td> {{ shipment.trackingNum }} </td>
      <td> {{ shipment.sender }}</td>
      <td> {{ shipment.receiver }}</td>
      <td> {{ shipment.status }}</td>
  
     <!-- delete button --> 
     <td> <button @click="deleteShipment(index)">delete</button></td>
     <!-- edit button --> 
     <td> <button @click="toShowEditShipment(index)">edit</button></td>
    </tr>
  </table>

      <!-- list search -->
  </div>
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
      <!-- warning -->
  <div>
  <p :style="warningStyle" v-if="textDisplay=='noSearch'"> ----- กรุณาใส่หมายเลขพัสดุ -----</p>
  <p :style="warningStyle" v-else-if="textDisplay=='wrongTrack'"> ----- ไม่พบข้อมูลการค้นหา -----</p>
  </div>

      <!-- add form -->
  <button @click="toShowForm">  เพิ่มหมายเลขพัสดุ </button>
  <div v-show="showForm">
  <p> Tracking No. : <input type="text" v-model="newTrack"></p>
  <p> Sender : <input type="text" v-model="newSender"></p>
  <p> Receiver : <input type="text" v-model="newReceiver"></p>
  <p> Status : <select v-model="newStatus">
    <option value="Picked up"> Picked up </option>
    <option value="In transit"> In transit </option>
    <option value="Delivered"> Delivered </option>
  </select></p>
  
  <button @click="addNewShipment"> submit </button>
  </div>

      <!-- edit form -->
<div v-show="showEditShipment">
  <p> Tracking No. : {{trackNum}} </p>
  <p> Sender : <input type="text" v-model="senderUpdate"></p>
  <p> Receiver : <input type="text" v-model="receiverUpdate"></p>
  <p> Status : <select v-model="statusUpdate">
    <option value="Picked up"> Picked up </option>
    <option value="In transit"> In transit </option>
    <option value="Delivered"> Delivered </option>
  </select></p>
  
  <button @click="editShipment"> submit </button>
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
