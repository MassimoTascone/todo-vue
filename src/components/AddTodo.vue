<template>
    <div class="form">
        <form @submit="addTodo">
            <input v-model="title" type="text" name="title" class="input" placeholder="Add a todo ...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: 'AddTodo',
    data() {
        return {
            title:''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: true
            }
            // send up to parent .vue
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>


<style scoped>

    form {
        display: flex;
        bottom: fixed;
        bottom: 0;
    }

    .input {
        flex:5;
        padding:15px;
        border: none;
        background-color: #f2f2f2;
        border-radius: 15px;
        font-size: 18px;
        margin-right: 15px;
        margin-left: 15px;
    }
    .input:focus {
        outline: none;
    }
    .btn {
        flex: 1;
        border:none;
        background-color: #41B883;
        border-radius: 15px;
        font-size: 18px;
        font-weight: bold;
        color: white;
    }

    .btn:hover {
        background-color: rgba(65, 184, 131, 0.561);
        cursor: pointer;
        color: #2c3e50;
    }
    .form {
        width:100%;
        max-width:1280px;
              margin: 0 auto;

    }
</style>