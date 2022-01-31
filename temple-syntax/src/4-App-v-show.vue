<script setup>
const isPresent = true
const msg = ''
</script>
 
<template>
<div>
  <p v-show="!isPresent">Prawit Nakee</p>
  <p v-show="isPresent">Prayut Narak</p>
  </div>
 
  <p>Your message is {{ msg }}</p>
  <p v-show="!msg" style="color: red">Please sleep</p>
 
</template>
