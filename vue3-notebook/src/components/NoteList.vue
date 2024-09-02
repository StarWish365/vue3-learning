<template>
    <ul id="task-list">
    <li v-for="(item,index) in list" :key="item.id">
        <div>
            <span>{{index+1}}. {{item.name}}</span>
            <button @click = "del(item.id)">删除</button>
        </div>
    </li>
    </ul>
</template>

<script setup>
import { inject } from 'vue'
const list = inject("list")

const emit = defineEmits(['delID'])
const del = (id) => {
    emit('delID', id)
}
</script>

<style>

</style>