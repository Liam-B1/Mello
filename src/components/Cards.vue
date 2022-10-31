<template>
    <div class="card">
        <h2>New Card!</h2> 
        <p>Add some tasks here:</p>
        <ul class="task-list">

        </ul>
    </div>
</template>

<style scoped>

.card{
    display: flex;
    flex-direction: column;
    width: 325px;
    height: 325px;
    background-color: #99D6EA;
    border: 5px;
    margin-top: 40px;
    margin-left: 50px;
    border-radius: 12px;
}

h2 {
    color: black;
    width: 110px;
    height: 35px;
    background-color: white;
    border-radius: 12px;
    font-size: 18px;
    text-align: center;
    margin-left: 10px;
}

p {
    color: white;
    align-self: center;
    font-size: larger;
}

ul li{
    align-self: center;
    color: white;
}

</style>