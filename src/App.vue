<template>
    <Nav/>

    <router-view></router-view>
</template>

<script setup>
import http from '@/services/http.js';
import Nav from '@/components/Nav.vue'

</script>
