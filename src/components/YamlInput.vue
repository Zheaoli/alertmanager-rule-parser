<template>
    <n-space class="p-4">
      <n-input type="textarea" v-model:value="yamlContent" style="min-height: 576px; background: linear-gradient(to right, gray-200, gray-500);" autosize />
    </n-space>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';
  
  export default {
    name: 'YamlInput',
    setup() {
      const yamlContent = ref('');
      return { yamlContent };
    }
  }
  </script>
  