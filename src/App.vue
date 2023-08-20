<template>
  <n-config-provider>
    <div class="h-screen bg-gradient-to-br from-yellow-100 to-yellow-300 flex items-center justify-center">
      <n-space class="p-6 bg-gradient-to-br from-yellow-200 to-yellow-400 rounded-lg shadow-xl" direction="vertical" align="start">
        <YamlInput v-model:value="yamlContent" />
        <FileUploadButton @file-loaded="updateYamlContent" />
        <n-button @click="processYaml">Process YAML</n-button>
        <OutputArea v-if="showOutput" :output="output" />
      </n-space>
    </div>
  </n-config-provider>
</template>

<script lang="ts">
import { ref } from 'vue';
import YamlInput from './components/YamlInput.vue';
import FileUploadButton from './components/FileUploadButton.vue';
import OutputArea from './components/OutputArea.vue';

export default {
  components: {
    YamlInput,
    FileUploadButton,
    OutputArea
  },
  setup() {
    const yamlContent = ref('');
    const output = ref('');
    const showOutput = ref(false);

    const updateYamlContent = (content: string) => {
      yamlContent.value = content;
    };

    const processYaml = () => {
      output.value = yamlContent.value;
      showOutput.value = true;
    };

    return {
      yamlContent,
      output,
      showOutput,
      updateYamlContent,
      processYaml
    };
  }
}
</script>
