<script setup lang="ts">
import { computed, ref } from 'vue';
import { marked } from 'marked';
import DOMPurify from 'dompurify';

const inputContent = ref('# hello')
const outputContent = computed(() => DOMPurify.sanitize(marked(inputContent.value) as string))
</script>
<template>
  <div class="flex h-screen">
    <textarea class="bg-gray-100 w-[50%] p-5 font-mono focus:outline-0 resize-none min-h-screen" v-model="inputContent" />
    <div class="p-5 w-6/12" v-html="outputContent"></div>
  </div>
</template>
<style></style>