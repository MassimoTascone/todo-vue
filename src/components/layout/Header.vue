<template>
    <header class="header">
        <h1>Todo Vue</h1>
    </header>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css?family=Lobster&display=swap');

    .header {
        font-family: 'Lobster', cursive;
        background-color:#41B883;
        color:white;
        margin-bottom: 10vh;
        top: 0;
        height: 5vh;
        display: flex;
    }

    h1 {
        padding: 0;
        margin: 0;
        font-size: 25px;
        padding-left: 20px;

    }
</style>