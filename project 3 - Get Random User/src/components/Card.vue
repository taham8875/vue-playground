<template>
  <img :class="userGender" :src="userImage" alt="User Image">
  <h3>{{ userName }}</h3>
  <div>Email: {{ userEmail }}</div>
  <button @click="getRandomUser">Get Random User</button>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const userImage = ref('');
const userName = ref('');
const userEmail = ref('');
const userGender = ref('');

getRandomUser();

async function getRandomUser() {
  const res = await fetch('https://randomuser.me/api');
  const { results } = await res.json();
  userImage.value = results[0].picture.large;
  userName.value = results[0].name.first + ' ' + results[0].name.last;
  userEmail.value = results[0].email;
  userGender.value = results[0].gender
}
</script>

<style scoped>
img {
  border-radius: 50%;
  width: 200px;
  height: 200px;
  object-fit: cover;
  margin-bottom: 1rem;
}

.male {
  border: 4px solid #2196f3;
}

.female {
  border: 4px solid #e91e63;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 0.25rem;
  background-color: #2196f3;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
  margin-top: 1rem;
}
</style>