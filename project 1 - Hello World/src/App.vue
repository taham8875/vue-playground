<script setup lang="ts">
import { ref } from 'vue';
import List from './components/List.vue';
import Form from './components/Form.vue';

const helloWorld = ref('Hello World!');
const color = ref('red');

function reverseMessage() {
    helloWorld.value = helloWorld.value.split('').reverse().join('');
}

function notify() {
    alert('You clicked the link!');
}

function toggleColor() {
    color.value = color.value === 'red' ? 'green' : 'red';
}
</script>

<template>
    <div>
        {{ helloWorld }}
        <br />
        This is a Vue 3 Hello World example.
    </div>
    <button @click="reverseMessage">
        Reverse Message
    </button>
    <button @click="helloWorld += '!'">
        Append !
    </button>
    <a href="www.google.com" @click.prevent="notify">
        A link that prevent default
    </a>
    <div :style="{ color }" @click="toggleColor">
        Click here to toggle the color
    </div>

    <List />
    <Form />
</template>

<style scoped>
* {
    display: block;
    margin: 15px;
}
</style>