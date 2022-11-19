<script setup>
import { ref } from 'vue';

const emit = defineEmits(['create'])
const name = ref(null)
const creating = ref(false)

const create = () => {
    name.value = null
    creating.value = ! creating.value
}

const save = () => {
    if(name.value !== null && name.value.trim() !== ''){
        emit('create', name.value)
        name.value = null 
        creating.value = false
    }
}
</script>


<template>
    <div class="newItem">
        <a class="new-item-button" href="#" @click.prevent='create'>+ New Item</a>

        <input v-if="creating" type="text" v-model="name" placeholder="Title" @keypress.enter="save"/>
    </div>
</template>

<style scoped>
a {
    color: white;
}

input{
    display: flex;
    justify-content: center;
    margin-top: 10px;
    padding: 3px;
    margin-left: 80px;
    border-radius: 4px;
    border: none,
}

.new-item-button{
    display: flex;
    justify-content: center;
    margin-top: 20px;
}
.new-item-button:hover{
    background-color: white;
    color: #6798C0;
    border-radius: 3px;
}



</style>