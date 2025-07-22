<script setup>
import CircleTab from './components/CircleTab.vue'
</script>
  
<template>
  <CircleTab 
    :data="[
      {outcome: 'Foo', values: {A: 0.1, B: 0.2, C: 0.3}},
      {outcome: 'Bar', values: {A: 0.4, B: 0.3, C: 0.1}},
      {outcome: 'Baz', values: {A: 0.2, B: 0.8, C: 0.2}}
    ]"
    :maxVal="1"
  />
</template>

<style scoped>
</style>
