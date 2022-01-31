<script setup>
const subjects = ['INT201', 'INT202', 'INT203', 'INT204']
</script>
 
<template>
  <ul>
      <li v-for ="(subject, index) in subjects" :key="index">
          index {{ index }}-{{ subject }}
      </li>
  </ul>
</template>
 
<style>

</style>