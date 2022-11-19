<script setup>
import Nav from './components/Nav.vue';
import CardButton from './components/CardButton.vue';
import CardBoard from './components/CardBoard.vue';
import Card from './components/Items.vue'




</script>

<template class="body">
    <title></title>
    <header>
    </header>

    <div class="nav">
      <Nav></Nav>
    </div>

    <div class="cardboard">
      <CardBoard/>
    </div>
    
  
</template>

<style scoped>

.button {
  display: flex;
}

main{
  height: auto;
  width: auto;
}

.cardboard {

  display: flex;
  flex-direction: row;
}

</style>
