<template>
    <h1>Index pagse</h1>

    <p>
        <span>Name:</span>
        <span>{{ name }}</span>
    </p>
    <p>
        <span>age:</span>
        <span>{{ age }}</span>
    </p>
    <button @click="handleClick">raname</button>
    <botton @click="">console.log.name</botton>
    <button @click="handleAddage">บวกอายุ</button>
</template>
<script setup>
//const name = "Thanapat"
const name = ref("init")
const age = ref(0)

const handleAddage = () =>{   
    let newage = age.value
    newage = newage +1

    age.value = newage
}
const handleShowLogName = () =>{
    //get
    const nameValue = name.value
    console.log(nameValue)
}
const handleClick = () => {
    //logig
    console.log('worked from handleClick function')
    // วิธีการเปลี่ยนค่า
    name.value = "Thanapat"
}
</script>