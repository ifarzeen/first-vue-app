<template>
  <div id="app">

    <Header/>

    <AddTodo/>

    <Todos v-bind:todos="todos" 
    v-on:del-todo="deleteToDo"/>
    
  </div>
</template>

<script>

import Header from './components/Layout/header';
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'


export default {
  name: 'App',
  components: {
     Header,
     Todos,
     AddTodo
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title: "Todo One",
          completed:false
      },
      {
          id:2,
          title: "Todo Two",
          completed:true
      },
      {
          id:3,
          title: "Todo Three",
          completed:true
      }
      ]
    } 
     
    },

    methods:{
      deleteToDo(id){
        this.todos=this.todos.filter(todo => todo.id !== id);
      }
    }
  }
</script>

<style>
*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
</style>
