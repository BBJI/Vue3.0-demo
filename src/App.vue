<script setup>
import Example1 from './components/example1/index.vue'
import Example2 from './components/example2/index.vue'
import Example3 from './components/example3/index.vue'
import Example4 from './components/example4/index.vue'
import Example5 from './components/example5/index.vue'
</script>

<template>
  <Example1 title="示例1：绑定的原理改变" />
  <Example2 />
  <Example3 />
  <Example4 />
  <Example5 />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
