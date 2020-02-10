<template>
<div id="main">
    <div id="todos">
        <h2>Todos</h2>
        <div v-bind:key="todo.id"   v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</div>
</template>
<script>
import TodoItem from './TodoItem.vue';

export default {
    name: 'Todos',
    components: {
        TodoItem
    },
    props:['todos']
}
</script>


<style>
#todos {
    min-height: 40vh;
}

</style>