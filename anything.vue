<template>
    <a href="#" @click="view('home')">Home</a>
    <a href="#" @click="view('counter')">Counter</a>

    <NuxtPage />

    <lazyHomeWelcome v-if="page == 'home'"/>
    <lazyCounter v-if="page == 'counter'"/>
</template>

<script setup>
const page = ref("home");

function view(name){
    page.value = name;
}
</script>
