<script setup>
import { onBeforeUnmount, onUnmounted } from 'vue'
defineProps({
    currentNum: {
        type: Number
    }
})
</script>
 
<template>
  current num: {{ currentNum }}
</template>
 
<style scoped>

</style>