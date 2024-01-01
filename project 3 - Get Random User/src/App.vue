<template>
  <div class="container">
    <Card />
  </div>
</template>

<script setup lang="ts">
import Card from './components/Card.vue';

</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f5f5f5;
}
</style>