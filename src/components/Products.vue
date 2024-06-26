<template>
<ul>
    <slot v-for="(product, index) in products" :key="index" v-bind:product="product"></slot>
</ul>
</template>

<script>

export default {
    name: 'Products.vue',
    props: ['products']
}

</script>