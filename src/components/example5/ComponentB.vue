<script setup>
    import { getCurrentInstance, onBeforeUnmount, onMounted } from "vue";
    import Component from '../example1/index.vue'
    const instance = getCurrentInstance()
    const emit = defineEmits(['getData'])
    defineExpose({
        getComponent: () => instance
    })
    defineProps({
        title: String
    })
    onMounted(() => {
        console.log('ComponentB已挂载', getCurrentInstance())
    }) 
    onBeforeUnmount(() =>{
        console.log('ComponentB已卸载')
    })
</script>

<template>
    <component :is="Component" :title="title"></component>
    <button @click="emit('getData', 'getData from ComponentB')">getData</button>
</template>