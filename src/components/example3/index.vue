<script setup>
    import { reactive, watch, watchEffect, computed } from 'vue';
    const data = reactive({ count: 0 });

    watch(() => data.count, (newCount, oldCount) => {
        console.log(`count 从 ${oldCount} 变为 ${newCount}`);
    });

    watchEffect(() => {
        console.log(`count 的值为 ${data.count}`);
    });

    const doubleCount = computed(() => data.count * 2);
    const add = () => {
        data.count++
    }
</script>

<template>
    <h2>示例3：watch, watchEffect, computed</h2>
    <button @click="add">add</button>
    <div>count: {{ data.count }}</div>
    <div>doubleCount: {{ doubleCount }}</div>
</template>
