<script setup lang="ts">
import { ref } from 'vue';

const text = ref('Edit me');
const checked = ref(false);
const checkedNames = ref([]);
const picked = ref('One');
const selected = ref('');
const multipleSelected = ref([]);
</script>

<template>
    <h2>Text Input</h2>

    <input v-model="text" type="text">

    {{ text }}

    <h2>Check box</h2>

    <input type="checkbox" value="checkbox" id="checkbox" v-model="checked">
    <label for="checkbox">Checkbox: {{ checked }}</label>

    <h2>Multi check box</h2>

    <pre>
{{ checkedNames }}
    </pre>

    <input type="checkbox" value="john" id="john" v-model="checkedNames">
    <label for="john">john</label>

    <input type="checkbox" value="jane" id="jane" v-model="checkedNames">
    <label for="jane">jane</label>

    <input type="checkbox" value="joe" id="joe" v-model="checkedNames">
    <label for="joe">joe</label>

    <h2>Radio</h2>

    <input type="radio" value="One" id="one" v-model="picked">
    <label for="one">One</label>

    <input type="radio" value="Two" id="two" v-model="picked">
    <label for="two">Two</label>

    <h2>Select</h2>

    <select v-model="selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
    <span> selected: {{ selected }}</span>

    <h2>Multiple Select</h2>

    <select v-model="multipleSelected" multiple style="width: 100px;">
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>

    <span> selected: {{ multipleSelected }}</span>
</template>
