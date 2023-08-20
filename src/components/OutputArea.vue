<template>
    <n-space class="p-4 mt-4" direction="vertical">
      <n-card>
        <pre>{{ output }}</pre>
      </n-card>
    </n-space>
  </template>
  
  <script lang="ts">
  export default {
    name: 'OutputArea',
    props: {
      output: {
        type: String,
        default: ''
      }
    }
  }
  </script>
  