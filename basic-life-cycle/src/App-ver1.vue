<script setup>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue'
import NumUpdate from '.components/NumUpdate.vue'
onMounted(() => alert('on mounted, ${num.value}'))
onBeforeMount(() => alert('on before mount,${num.value}'))

onBeforeUpdate(() => {
   num.value = num.value > 2 ? 1 : num.value
   alert ('on before update, ${num.value}')
})

onUpdated(() => alert('on updated, ${num.value}'))
const num = ref(1)

const hasUpdate = ref(true)
const closeUpdate = () => (hasUpdate.value = false)
</script>
 
<template>
 <div>Num: {{ num }}</div>
 <div>
   <button @click="num = num + 1">+</button>
 </div>
 <div>
   <NumUpdate :currentNum="num" v-if="hasUpdate" />
   <button @click="closeUpdate">Not allow to Update</button>
 </div>
</template>
 
<style scoped>

</style>