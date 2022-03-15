<script setup>
import {onBeforeMount, ref} from 'vue'
import NoteList from './components/NoteList.vue'
import CreateNoteVu from './components/CreateNote.vue';
const notes=ref([])

// GET method
const getNotes = async ()=> {
  const res= await fetch('http://localhost:5000/notes')
  // console.log(res.json())
  // notes.value = res.json()
  // console.log(notes.value)
  //  const res = await fetch('http://localhost:5000/notes')
  if (res.status === 200) notes.value = await res.json()
  else console.log('not found')



}

onBeforeMount( async ()=>{
  // getNotes()
  await getNotes()
  console.log(notes.value)
})


// DELETE method
const removeNote = async (deleteNoteId) => {
  const res = await fetch(`http://localhost:5000/notes/${deleteNoteId}`, {
    method: 'DELETE'
  })
  if (res.status === 200) {
    notes.value = notes.value.filter((note) => note.id !== deleteNoteId)
    console.log('deleted successfully')
  } else console.log('error, cannot delete')
}


// CREATE method
const createNewNote = async (newNoteDetail) => {
  // console.log(newNote)
  const res = await fetch('http://localhost:5000/notes', {
    method: 'POST',
    headers: {
      'content-type': 'application/json'
    },
    body: JSON.stringify({
      noteDetail: newNoteDetail
    })
  })
  if (res.status === 201) {
    const addedNote = await res.json()
    notes.value.push(addedNote)
    console.log('added successfully')
  } else {
    console.log('error, cannot add')
  }
}


// EDIT

</script>
 
<template>
  <div>
    <CreateNote @createNote="createNewNote" />
    <NoteList :notes="notes" @deleteNote="removeNote" />
  </div>
</template>
 
<style scoped>

</style>