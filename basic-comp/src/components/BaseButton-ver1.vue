<script setup>
import { ref } from 'vue'
const prop = defineProps({
  yourText: {
    type:String,
    require:true
  }
}) 

console.log(prop.yourText)
// prop.yourText = 'Confirm'

const buttonText = ref(prop.yourText)
// buttonText.value = 'Confirm'       -- ไม่ควรทำ (รับมาแล้วอยู่ ๆ มาทำได้ไง)
</script>
 
<template>
  <button class="button-color" >{{ buttonText }}</button> <br>
  
</template>
 
<style scoped>
.button-color {
  background-color: aquamarine;
}

</style>