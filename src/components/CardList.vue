<script setup>
import Items from './Items.vue';
import { ref } from 'vue';
import NewItemButton from './NewItemButton.vue';

// emit we are sending to the Cardboard
const emit = defineEmits(['update-list-title', 'create', 'deleteList']);

// 
const props = defineProps({
    list: {
        type: Object,
    },
   
});

const editing = ref(false)
const listTitleEdit = ref(null)

const edit = () =>{
    editing.value = true
};

const saveEdit = () =>{
     emit('update-list-title', listTitleEdit.value.value)
     editing.value = false
    
};

const deleteList = () =>{
    emit('delete-list')
}

</script>


<template>
    <div class="container">
        <div class=list-heading>
            <h2 @click="edit">{{editing ? '&nbsp;' : list.title }}</h2>
            <button class="deleteList" @click="deleteList"></button>
            <input v-if="editing" 
                type="text" 
                placeholder="Title" 
                class="heading"
                @change="saveEdit"
                :value="list.title"
                ref="listTitleEdit"/> 
            </div>
            <div class="list-body">
                <Items 
                v-for="Items in list.cards" 
                :key="Items.id"
                :card="Items"
                ></Items>
                <!-- this commponents is listing to a function from 'newItemButton then passing to the board' -->
                <NewItemButton  @create="(name) => $emit('create-card', name)"
                ></NewItemButton>
        </div>
    </div>
</template>

<!-- @click(emited value from child element) -->


<style scooped>
.container {
    border-radius: 4px;
    padding: 10px;
    background-color: #6798C0;
    color: white;
    width: 250px;
    height: 200px;
    Margin: 20px;
    align-content: center;
}

.item:hover{
    cursor: pointer;
    background-color: whitesmoke;
    color: black;
}

.list-heading{
    display: flex;
    justify-content: space-between;
    margin-left: 5px;
    
}

.list-heading:hover{
    background-color: white;
    color: #6798C0;
    border-radius: 3px;
}

.deleteList{
    width: 20px;
    height: 20px;
    margin-right: 5px;
    margin-top: 25px;
    background-color: white;
    color: #6798C0;
    cursor: pointer;
    border: none;
    border-radius: 3px;
}

.heading{
    position: fixed;
    align-self: center;
    margin-left: 3px;
    padding: 10px;
}

Items{
    background-color: white;
}

h2{
    display: flex;
    justify-content: center;
    cursor: pointer;
}

</style>
