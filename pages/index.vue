<template>
  <div id="app" class="app">
    <AppTextEditor :content="content" @update-content="handleUpdateContent" :max-limit="280" />
    <!-- <AppTextEditor :modelValue="content" @update:modelValue="content = $event.target.value" :max-limit="280" /> -->
    <button class="submit-button" @click="onSubmit">Submit</button>
  </div>
</template>

<script setup lang="ts">
import AppTextEditor from '../components/AppTextEditor.vue';

const content = ref<string>('');

function onSubmit() {
  alert(JSON.stringify(content.value))
}

function handleUpdateContent(value: string) {
  content.value = value;
}
</script>

<style scoped>
.app {
  font-family: Arial;
  font-size: 16px;
}

.submit-button {
  border: 1px solid #333;
  border-radius: 2px;
  background: #fff;
  color: #333;
  font-size: 16px;
  padding: 6px 12px;
  margin-top: 8px;
  -webkit-appearance: none;
  cursor: pointer;
}

.submit-button:hover {
  background: #333;
  color: #fff;
}
</style>
