<script setup>
const userLoggedIn = false
</script>

<template>
<div>
  <div v-if="userLoggedIn">
        <h2>Hello Welcome!</h2>
        <p>You have sucessfully logged in!</p>
  </div>
  <div v-else>
        <p>Please Log In to access your account!</p>
    </div>
  <div>
        <button v-if="!userLoggedIn">Login</button>
        <button v-else>LogOut</button>
  </div>
</div> 
</template>

<style></style>

