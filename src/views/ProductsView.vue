<template>
  <Products :products="products" v-slot="props">

    <li @click="getProducts(props.product.id)">{{ props.product.name }}</li>

  </Products>
</template>

<script>
import Products from '@/components/Products.vue';

export default {
  components: {
    Products
  },

  data(){
    return {
      products:[
        {
          id:1,
          name:'Imac'
        },
        {
          id:2,
          name:'MacBook'
        },
        {
          id:3,
          name:'IdeaPad'
        }
      ]
    }
  },

  methods: {
    getProducts(id){
      console.log(id);
    }
  },
}

</script>
