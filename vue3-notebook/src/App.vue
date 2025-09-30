<template>
  <div class="container">
    <h1>任务列表</h1>
    <NoteHeader @addTask="addTask"></NoteHeader>
    <NoteList @delID="delID"></NoteList>
    <NoteFooter></NoteFooter>
  </div>
</template>

<script setup>
import NoteHeader from "./components/NoteHeader.vue";
import NoteList from "./components/NoteList.vue";
import NoteFooter from "./components/NoteFooter.vue";
import{ref, provide} from "vue";
const list = ref([
  {id:1, name:"跑步"},
  {id:2, name:"学习"},
  {id:3, name:"整理"}
])
provide("list", list)
const addTask = (toDo) =>{
  list.value.push({
    id: +new Date(),
    name: toDo
  })
}
const delID = (id) =>{
  list.value = list.value.filter(item=>item.id!==id)
}

</script>

<style>

</style>