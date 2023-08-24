<script setup>
    import { nextTick, reactive, ref } from 'vue';

    const dom = ref() 
    const data = reactive({ count: 0 });
    const add = () => {
        data.count++
        console.log('dom更新前执行：', dom.value.innerText)
        nextTick(() => {
            console.log('dom更新后执行：', dom.value.innerText)
        })
    }
</script>

<template>
    <h2>示例4：nextTick</h2>
    <button @click="add">add</button>
    <div ref="dom">{{ data.count }}</div>
</template>
