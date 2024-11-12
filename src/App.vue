<script setup lang="ts">
import Todos from './components/Todos.vue'
import { ref } from 'vue';
var users = ref(null);
fetch("http://localhost:3000/user").then(response => response.json())
.then(data => users = data);
</script>

<template>
  <main>
    <h1>TEST APP AWPLIFY</h1>
    <ul class="mb-0" v-if="users != null">
                    <li v-for="user in users">{{user}}</li>
                </ul>
    <Todos />
  </main>
</template>

