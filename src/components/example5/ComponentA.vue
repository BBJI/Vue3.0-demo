<script setup>
    import { onMounted, onBeforeUnmount, getCurrentInstance, inject } from "vue";
    import Component from '../example1/index.vue'
    const instance = getCurrentInstance()
    const message = inject('message')
    const emit = defineEmits(['getData'])
    defineExpose({
        getComponent: () => instance
    })
    defineProps({
        title: String
    })
    onMounted(() => {
        console.log('ComponentA已挂载')
    }) 
    onBeforeUnmount(() => {
        console.log('ComponentA已卸载')
    })
    const getProvideFromParent = () => {
        console.log('inject message', message)
    }
</script>

<template>
    <component :is="Component" :title="title"></component>
    <button @click="emit('getData', 'getData from ComponentA')">getData</button>
    <button @click="getProvideFromParent">getProvideFromParent</button>
</template>