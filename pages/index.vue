<script setup>
useHead({
    title: 'Home Page',
    meta: [
        {
            name: 'Tekfolio',
            content: 'The main page of the website'
        }
    ]
});

definePageMeta({
    layout: 'default'
});

// Fetch data and assign it to a variable
const { data } = await useFetch('/api/userdetails');
</script>

<template>
    <h1>Home Page</h1>
    <p>{{ data?.msg }}</p> <!-- Use optional chaining to avoid errors if data is null/undefined -->
    <NuxtLink to="/about">About Us</NuxtLink>
</template>
