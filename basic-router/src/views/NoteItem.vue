<script setup>
// useRoute to get params
import { useRoute } from 'vue-router'
let { params } = useRoute()
console.log(params.noteId)

// use Router to get router object
const appRouter = useRoute()
const goBack= () => appRouter.go(-1)

const goAboutUs = () => appRouter.push({ name: 'About' })
</script>
 
<template>
 <div>
     <h1>NoteItem</h1>
     <p>your selected note is {{ this.$route.params.noteId }}</p>
     <button @click="goBack">Back</button>
     <button @click="goAboutUs">AboutUs</button>
 </div>

</template>
 
<style scoped>

</style>