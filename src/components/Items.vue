<script setup>
import {ref} from "vue"
import modal from "./modal.vue";

const props = defineProps({
    card: {
        type: Object,
    }
})

const modalOpen = ref(false)

</script>

<!-- #header is a header slot class from modal -->
<template>
    <div class="card" @click="modalOpen = true">
        {{card.title}}
    </div>
    <modal v-if="modalOpen" :open="modalOpen" @close="modalOpen = false">
        <template #header>
            <h2>{{card.title}}</h2>
        </template>
        <template #body>
            {{card.content}}
        </template>

    
    </modal>
</template>



<style scoped>

.title-edit{
    position: absolute;
}


h2 {
    color: white;
    background-color: #6798C0;
    display: flex;
    justify-content: center;

}



.card{
    background-color: white;
    border-radius: 3px;
    margin: 5px;
    padding: 3px;
    padding-left: 7px;
    color: #6798C0;
    cursor: pointer;
    margin-top: 10px;
}

</style>