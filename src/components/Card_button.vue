<script setup>
import Cards from './Cards.vue';
import Board from './Board.vue'


const addCard = () =>{

}

</script>


<template>
    <button @click="addCard">Card +</button>
</template>

<style scoped>
button {
    display: block;
    justify-content: center;
    text-align: center;
    width: 160px;
    height: 68px;
    padding: 10px;
    font-size: 24px;
    margin-top: 24px;
    border-radius: 25px;
    background-color: #6798c0;
    border-color: #6798c0;
    color: white;
}

button:hover{
    background-color: white;
    color: #6798c0;
}

</style>