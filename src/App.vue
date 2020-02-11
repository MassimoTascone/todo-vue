<template>
  <div id="app">
    <Header/>
        <div class="todo-container">
          <img alt="Vue logo" src="./assets/logo.png" width="100px" height="auto">
          <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
        </div>
        <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import Header from './components/layout/Header.vue'
import AddTodo from './components/AddTodo.vue'

export default {
  name: 'app', 
  components: {
    Todos,
    Header,
    AddTodo,
  },
  data(){
    return{
      todos:[
      {
      id: 1,
      title:'Saying Hi to Chin',
      completed: true
    },
    {
      id: 2,
      title:'Saying Hi to Julien',
      completed: true
    },
    {
      id: 3,
      title:'Saying Hi to Matis',
      completed: true 
    }
    ]
  }
},
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }

}
    
</script>

<style>

  body {
    margin: 0;
    padding: 0;



  }

  #app {
    margin: 0;
    padding: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    font-size: 20px;
    height: 100vh;
    display: grid;
    grid-template-rows: 20vh 1fr 20vh;

  }
  Header {
    grid-row: 1/2;
  }
  .todo-container{

      width:100%;
      max-width:1280px;
      margin: 0 auto;
      grid-row: 2/3;
  }


  .form {
    grid-row: 3/4;
  }


</style>



