<script setup>
const isItalic = true
const redText = 'color:red'
const italicText = 'font-style:italic'
</script>
 
<template>
<!-- style binding (array style) -->
<p :style="[redText, isItalic ? italicText : '']">
  Binding HTML Style (Array Syntax)
</p>
</template>
 
<style>
 
</style>