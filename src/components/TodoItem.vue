<template>
<!-- if todo-completed is true then change class to is-complete -->
    <div class="todo-item" v-bind:class="{'is-complete':!todo.completed}">
            <input type="checkbox" v-on:change="markComplete">

            <div class="todo-txt">
                <p class="todo-content">{{ todo.title }}</p>
            </div>
                
            <div class="del-btn">
                <a v-on:click="$emit('del-todo', todo.id)" class="del"><i class="fa fa-trash-o" aria-hidden="true"></i></a>
            </div>
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
        display: grid;
        grid-template-columns: 1fr 4fr 1fr
    }

    .todo-txt {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .todo-content {
        padding: 0;
        margin: 0;
    }
    .del-btn {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        
    }

    a {
        cursor: pointer;
        color: #2c3e50;
    }
    a:hover {
        color: rgb(148, 25, 13);
    }
    .del {
        width: 25px;
        height: 25px;
    }

    input[type=checkbox] {
        zoom: 2;
        grid-column: 1/2;
    }

    input[type=checkbox]:hover {
        cursor: pointer;
    }



</style>