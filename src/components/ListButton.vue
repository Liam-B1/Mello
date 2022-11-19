<script setup>
import {ref} from 'vue'

const emit = defineEmits(['create'])

const name = ref(null);
const creating = ref(null);

const create = () => {
    emit('create')
}
</script>

<template>
<div class="newList">
    <a id="listButton" href="#" @click.prevent="create">Add Another List</a>
</div>
</template>

<style scooped>
.newList{
align-self: center;
margin-left: 20px;
margin-right: 20px;
color: #6798C0;
}

#listButton{
    color: #6798C0;
}
</style>