<script setup>
import { ref } from 'vue'
defineEmits(['createNote'])
const noteDetail = ref('')
</script>
<template>
  <div>
    <h2>Create Notes</h2>
    Note Detail <input type="text" v-model="noteDetail" />
    <button @click="$emit('createNote', noteDetail)">Create</button>
  </div>
</template>
<style></style>