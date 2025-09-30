<template>
  <div class="input-container">
    <input v-model="toDo" type="text" placeholder="请输入任务" id="task-input">
    <button @click="add" id="add-task-button">添加任务</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const toDo = ref('')

//向父组件传参
const emit = defineEmits(['addTask'])
const add = () => {
  emit('addTask', toDo.value)
  toDo.value = ''
}

</script>

<style>

</style>