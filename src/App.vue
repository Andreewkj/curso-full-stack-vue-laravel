<template>
    <Nav/>

    <router-view></router-view>

    <button @click="count++">add count - {{ count }}</button>

    <CountChild v-on:addCount="plus" />
</template>

<script setup>
import Nav from '@/components/Nav.vue';
import CountChild from '@/components/CountChild.vue';

import {ref} from 'vue';

const count = ref(0);

function plus(){
    return count.value++
}

</script>
