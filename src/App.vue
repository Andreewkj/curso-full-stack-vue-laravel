<template>
    <Nav/>

    <router-view></router-view>

    <img src="https://picsum.photos/200/300" id="img" ref="img">
    <ul>
      <li v-for="(product, index) in products" id="lis">{{index}}{{ product.name }}</li>
    </ul>
</template>

<script setup>
import Nav from '@/components/Nav.vue';

import { ref, onMounted, reactive } from 'vue';

const img = ref(null);

onMounted(() => {
  // console.log(document.querySelector('#img'));
  console.log(img.value['src']);
})

const products = reactive([
  {
    id: 1,
    name:'Imac'
  },
  {
    id:2,
    name:'xps'
  }
])

</script>
