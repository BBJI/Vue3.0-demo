<script setup>
  import { reactive } from "vue"
  const props = defineProps(['title'])
  const data = {count: 0}
  const reactiveData = reactive(data)
  const add = () => {
    reactiveData.count++
  }
</script>

<template>
  <h2>{{ props.title }}</h2>
  <button @click="add">add</button>
  <div>{{ reactiveData.count }}</div>
</template>
