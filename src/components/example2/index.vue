<script setup>
import { onMounted, reactive } from "vue";
const data = { content: ['组件挂在中'] }
const reactiveData = reactive(data)
    onMounted(() => {
        reactiveData.content.push('组件已挂载')
    })
</script>

<template>
    <h2>示例2：setup</h2>
    <div>{{ reactiveData.content }}</div>
</template>
