<script setup>
const password = "1234569999"
</script>

<template>
<p v-if="password.length < 5">Weak</p>
<p v-else-if="password.length <= 8">moderate</p>
<p v-else>Strong Password</p>
</template>

<style></style>

