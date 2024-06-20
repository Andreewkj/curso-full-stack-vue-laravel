<template>
    <form action="" @submit.prevent="create">
        <input type="text" placeholder="firstName" v-model="user.firstName" style="display: block;">
        <span v-if="errors.message.firstName"> {{ errors.message.firstName[0] }}</span>
        <input type="text" placeholder="lastName" v-model="user.lastName" style="display: block;">
        <span v-if="errors.message.lastName"> {{ errors.message.lastName[0] }}</span>
        <input type="text" placeholder="email" v-model="user.email" style="display: block;">
        <span v-if="errors.message.email"> {{ errors.message.email[0] }}</span>
        <input type="text" placeholder="password" v-model="user.password" style="display: block;">
        <span v-if="errors.message.password"> {{ errors.message.password[0] }}</span>
        <button type="submit" style="display: block;">Cadastrar</button>
    </form>
</template>

<script setup>

import http from '@/services/http.js';
import {reactive} from 'vue';

const user   =  reactive({});
const errors = reactive({message:{}});

async function create() {
    try {
        const {data} = await http.post('/api/user', user);
        //console.log(data);
    } catch (error) {
        if (error) {
            errors.message = error.response.data['errors'];
        }
    }
}

</script>

<style lang="scss" scoped>

</style>