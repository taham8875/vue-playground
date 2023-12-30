<script setup lang="ts">
import { ref } from 'vue';

const list = ref([1, 2, 3]);
const showList = ref(true);
</script>

<template>
    <button @click="showList = !showList">
        Toggle List
    </button>
    <button @click="list.push(list.length + 1)">
        Push Number
    </button>
    <button @click="list = list.slice(0, list.length - 1)">
        Pop Number
    </button>
    <button @click="list.reverse()">
        Reverse List
    </button>


    <ul v-if="showList && list.length">
        <li v-for="item in list" :key="item">
            {{ item }}
        </li>
    </ul>

    <div v-else-if="!list.length">
        List is empty
    </div>
    <div v-else>
        List is hidden
    </div>
</template>

<style></style>