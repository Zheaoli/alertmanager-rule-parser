<template>
    <n-space class="p-4 w-full">
      <div class="border-t-2 border-gray-400 my-4"></div>
      <n-upload
        :on-finish="fileUploaded"
        action="javascript:;"
        style="display: none"
      >
        <template #trigger>
          <div></div>
        </template>
        <template #default>
          <div></div>
        </template>
      </n-upload>
    </n-space>
  </template>
  
  <script lang="ts">
  export default {
    name: 'FileUploadButton',
    methods: {
      fileUploaded(info) {
        const fileReader = new FileReader();
        fileReader.onload = (event) => {
          this.$emit('file-loaded', event.target.result);
        };
        fileReader.readAsText(info.file);
      }
    }
  }
  </script>
  