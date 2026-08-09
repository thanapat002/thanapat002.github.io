<template>
    <h1>cart</h1>
    <div v-for="item in mycart">
        {{item.name}}
        <button @click="handleclickDelete(item.id)">ลบ</button>
    </div>
    <hr />
</template>
<script setup>
import mockProduct from "~/data/mock-products.json"

const mycart = ref([])
const getProducts = () =>{
const ls =  localStorage.getItem("products")
 
return ls
}

const handleclickDelete = (productId) =>{
console.log('id', productId)
const ls = getProducts()
const lsArray = JSON.parse(ls)
const result = lsArray.filter((item) => {
     return item !== productId
})
const resultStr = JSON.stringify(result)
localStorage.setItem("products", resultStr)
    updateteMycart()
}
 
const updateteMycart = () => {
   const productsLS = getProducts()
    const productsArray = JSON.parse(productsLS)

    const result =mockProduct.products.filter((item) =>{
//logic
return productsArray.includes(item.id)
    })
    console.log('result', result)
    mycart.value = result 
}

onMounted(() => {
    updateteMycart()
})
    
</script>