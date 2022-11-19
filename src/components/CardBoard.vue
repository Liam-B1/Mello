<script setup>
import CardButton from './CardButton.vue';
import CardList from './CardList.vue'
import ListButtonVue from './ListButton.vue';
import { ref, reactive } from 'vue';


// Masterlist/data
const lists = reactive([{
    id: '1',
    title: 'Todo List:',
    cards: [{
        id: '2',
        title: 'New item',
        content: 'Things to do'
    }]
 }
]);
 
// updates list title inside list array
const updateListTitle = (listIndex, newTitle) =>{
    lists[listIndex].title = newTitle
}

// creates new list
const createList = () => {
    lists.push({
        id: '',
        title: ' New item',
        cards:[
        ]
    })
}


const createCard = (listIndex, title) => {
    lists[listIndex].cards.push({
        id: '',
        title: title,

    })
}

const deleteList = (listIndex) => {
    lists.splice(listIndex, 1)

}

 </script>


<template class="board">
    <ListButtonVue @create="createList"></ListButtonVue>  
        <CardList v-for="(list, index) in lists" 
        :list="list" 
        :key="list.id" 
        @update-list-title="(title) => updateListTitle(index, title)"
        @create-card="(name) => createCard(index, name)"
        @delete-list="() => deleteList(index)"
        >
    </CardList>
</template>


<style scoped>
.board{
    display: flex;
    margin-top: 20px;
    width: 500px;
    height: 500px;
    border-color: black;
    border-radius: 10px;
    flex-direction: row;
}

h2 {

}

</style>