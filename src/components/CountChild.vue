<template>
    <!-- <button @click="$emit('addCount')"> son </button> -->
    <button @click="add"> son </button>
</template>

<script setup>

const emit = defineEmits(['addCount']);

function add(){
    emit('addCount', 10)
}

</script>