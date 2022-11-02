<script setup>
import Cards from './Cards.vue'

const props = defineProps({
    item: [ ]


})

</script>



<template class="board">
    <ul class="list">
        <li>{{props.item}}</li>
    </ul>
</template>

<style scoped>
.list{
    border: 2px red;
    width: 100%;
    height: 100%;
}

</style> 

