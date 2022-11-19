<script setup>
import {ref} from 'vue';


const props = defineProps ({
    open: {
        
        type: Boolean,
        default: false
    }
})
</script>



<template>
    <div class="modal-background" v-if="open" @click.self="$emit('close')">
        <div class="modal">
            <div class="modal-heading">
                <slot name="header"></slot>

            </div>

            <div class="modal-body">
                <slot name="body"></slot>
            </div>

            <div class="modal-footer">
                <slot name="footer"></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
.modal-background {
    background: rgba(0, 0, 0, .5);
    display: flex;
    justify-content: center;
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
}

.modal {
    background: #6798C0;
    width:350px;
    height: fit-content;
    align-items: center;
    margin-top: 200px;
    border-radius: 4px;
}

.modal-heading {
    align-self: center;
    position: relative;

}
</style>