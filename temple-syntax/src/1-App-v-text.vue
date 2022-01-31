<script setup>
const msg = "Hello Vue.js"
const counter = 1
</script>
 
<template>
  <!--  <h1>Hello Vue.js</h1>  -->
  <h1>{{ msg.toLowerCase }}</h1>
  <!--  <p>{{ counter += 10 }}</p>  -->
  <p v-text="(counter += 10)"></p>
</template>
 
<style>
 
</style>