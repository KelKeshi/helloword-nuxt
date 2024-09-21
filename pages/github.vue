<script setup>
import { ref, onMounted } from 'vue';

const users = ref([]);

const userFetch = async () => {
    const response = await fetch('https://api.github.com/users');
    const data = await response.json();
    users.value = data;
};

onMounted(() => {
    userFetch();
});
</script>

<template>
    <h1>Github Users</h1>
    <div v-for="user in users" :key="user.id">
        <h2>{{ user.login }}</h2>
        <p>id is {{ user.id }}</p>

        <p>name: {{ user?.name }}</p>
    </div>
</template>
