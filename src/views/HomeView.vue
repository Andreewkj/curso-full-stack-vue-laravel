<template>
<div>
    <input type="text" v-model="user.firstName" placeholder="firstName">
    <input type="text" v-model="user.lastName" placeholder="lastName">

    <ul>
        <li v-for="item in items" :key="item.id">{{ item.name }} <input type="text" v-model="item.name"></li>
    </ul>
</div>
</template>

<script setup>

import {ref, watch, reactive} from 'vue';

const firstName = ref('');
const lastName = ref('');

watch([firstName, lastName], ([valueFirstName, valueLastName], [oldValueFirstName, oldValueLastName]) => {
    console.log('new => ' + valueFirstName, 'old => ' + oldValueFirstName);
})

const user = reactive({
    firstName:'',
    lastName:''
})

const items = reactive([
    {
        id: 1,
        name:'Alexandre'
    },
    {
        id:2,
        name:'João'
    },
])

// watch(() => 
//     user.firstName,
//         (value, oldValue) => {
//             console.log(value + '-' + oldValue);
//         }
//     )

watch(
    items, (value) => {
        value.forEach((item) => {
        if (!Number.isInteger(Number(item))) {
            console.log('not a number '+item.name);
        }
    })
})
</script>

