<script setup>
    import { ref, provide, inject, onMounted } from 'vue';

    import ComponentA from './ComponentA.vue';
    import ComponentB from './ComponentB.vue';
    const currentComponent = ref('ComponentA');
    const componentRef = ref()
    const components = {
        ComponentA,
        ComponentB
    }

    const toggleComponent = () => {
        currentComponent.value = currentComponent.value === 'ComponentA' ? 'ComponentB' : 'ComponentA';
        console.log('defineExpose getComponent:', componentRef.value.getComponent())
    };
    const getData = data => {
        console.log('defineEmits getData:', data)
    }
    provide('message', 'data from parent')
</script>

<template>
    <h2>示例5：keepAlive, getCurrentInstance</h2>
    <button @click="toggleComponent">切换组件</button>
    <br/>
    <keep-alive>
        <component :is="components[currentComponent]" :title="currentComponent" ref="componentRef" @getData="getData"></component>
    </keep-alive>
</template>
