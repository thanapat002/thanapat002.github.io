<template>
    <h1>Product</h1> 
    <div v-for="item in data.products">
        <div>ID: {{ item.id}} </div>
        <div>Name: {{ item.name}}</div>
        <div>
            <button @click="handleclickadd(item.id)">Add</button>
        </div>
    </div>
</template>

<script setup>
 import mockProduct from "~/data/mock-products.json"
 
 const data = ref([])
 const handleclickadd = (productId) =>{
console.log('productId', productId)
const ls = localStorage.getItem('products')
const lsArray = JSON.parse(ls) 
const products = lsArray || [] 
products.push(productId)
const productsStr = JSON.stringify(products)

 console.log('products', products)
localStorage.setItem('products', productsStr)
 }

//logic() => {} data.value = mocKProduct
 onMounted(() => {data.value = mockProduct
 console.log('assing done !')})
</script>