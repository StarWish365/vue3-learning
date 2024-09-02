<template>
    <div class="footer">
        <span>合计：{{list.length}}</span>
        <button id="clear-tasks-button">清空任务</button>
    </div>
</template>

<script setup>
import { inject } from 'vue'
const list = inject("list")
</script>

<style>

</style>