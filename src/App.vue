<script setup>
import Nav from './components/Nav.vue';
import Card_button from './components/Card_button.vue';
import Cards from './components/Cards.vue'
import Board from './components/Board.vue'



</script>

<template class="body">
    <title></title>
    <header>
    </header>
<main>
    <div class="nav">
    <Nav></Nav>
    </div>

    <div class="button">
      <Card_button></Card_button>
    </div>

    <Board></Board>
    <!-- <Cards></Cards> -->

  </main>
</template>

<style scoped>

.button {
  display: flex;
  justify-content: center;
}

main{
  height: auto;
  width: auto;
}

</style>
