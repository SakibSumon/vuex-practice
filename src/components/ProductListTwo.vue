<template>
  <ul id="product-list-two">
    <li v-for="(product, index) in products" :key="index" class="one-li">
      <h3>{{ product.name }}</h3>
      <p>{{ product.price }}</p>
    </li>
  </ul>
</template>

<script setup>
import { computed } from 'vue'
import { useStore } from 'vuex'

const store = useStore();

const products = computed(()=>{
  return store.state.products;
})
</script>

<style scoped>

.one-li{
    color: black;
}

#product-list-two{
    background: #D1E4FF;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    margin-bottom: 30px;
    padding: 10px 20px;
}
#product-list-two ul{
    padding: 0;
    list-style-type: none;
}
#product-list-two li{
    margin-right: 10px;
    margin-top: 10px;
    padding: 20px;
    background: rgba(255,255,255,0.7);
    text-decoration: none;
    list-style: none;
}
.price{
    font-weight: bold;
    color: #860CE8;
    display: block;
}
</style>