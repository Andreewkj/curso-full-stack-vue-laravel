<template>

  <img :src="img" alt="" srcset="">

  <button @click="count++">{{ count }}</button>

  <ul v-for="(user,key) in users">
    <li>{{key}} - {{ user.name }} with {{ user.age }}</li>
  </ul>
</template>

<script setup>
import { onMounted, onUpdated, ref, reactive } from 'vue';

const count = ref(0);

const img = 'https://picsum.photos/200';

const users = reactive([
  {
    name: 'Andreew',
    age: 27
  },
  {
    name: 'Jennifer',
    age: 21
  }
])

onMounted(() => {
  console.log('mounted');
})

onUpdated(() => {
  console.log(count.value);
})

</script>
