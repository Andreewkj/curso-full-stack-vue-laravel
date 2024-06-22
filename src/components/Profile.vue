<template>
    <p> cor preferida: {{ props.favoriteColor }}</p>
    <p> moto: {{ props.moto }}</p>
</template>

<script setup>

const props = defineProps({
    favoriteColor:String,
    moto:String
})

</script>

<style lang="scss" scoped>

</style>