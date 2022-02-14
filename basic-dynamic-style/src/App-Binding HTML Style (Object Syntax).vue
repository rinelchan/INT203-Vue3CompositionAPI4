<script setup>
const invalidMessage = 'red'
const italicText = 'italic'
const isItalic = false
const propItalic = 'font-style:italic'
const propRed = 'color:red'
</script>
 
<template>
<!-- style binding (object style) -->
  <input type="text"/>
  <p :style="{color:invalidMessage, 'font-style': italicText}">
    please input your text here
  </p>
  <p :style="{ color: isItalic ? 'red' : 'green' }">
    italic or coloring text
  </p>
</template>
 
<style>
 
</style>