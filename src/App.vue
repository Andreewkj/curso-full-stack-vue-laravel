<template>
    <Nav/>

    <router-view></router-view>
    <input type="text" name="" id="" placeholder="search" @keyup="search">
    <button>search</button>

</template>

<script setup>
import Nav from '@/components/Nav.vue';
import _ from 'lodash';

import { ref, onMounted, reactive } from 'vue';

const search = _.debounce(() => {
  console.log('search');
}, 1000)

// function search() {
//   console.log('search');
// }

</script>
