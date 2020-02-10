<template>
<!-- if todo-completed is true then change class to is-complete -->
    <div class="todo-item" v-bind:class="{'is-complete':!todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">{{ todo.title }}
            <button v-on:click="$emit('del-todo', todo.id)" class="del">X</button>
        </p>

    </div>
    
</template>

<script>
export default {
    
    // name of the component
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
    
}
</script>

<style scoped>

    .is-complete {
        text-decoration: line-through;
        color:rgb(204, 202, 202);
    }

    .todo-item {
        background-color: #F2F2f2;
        padding: 5px;
        margin-bottom: 10px;
        border-radius: 15px;
    }
    .del {
        background:rgb(194, 4, 4);
        color:white;
        border: none;
        padding: 10px 15px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
        font-size:20px;
    }
    .del:hover {
        background:rgb(146, 3, 3);

    }

    input[type=checkbox] {
        zoom: 2;
    }



</style>