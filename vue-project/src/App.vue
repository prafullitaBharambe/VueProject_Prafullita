<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  name: "TodoApp",
  components: {
    Todos,
    AddTodo
},
  data() {
    return {
      Todos: [
        {
          id: 1,
          title: "ES6",
          description: "Some course",
          status: false,
        },
        {
          id: 2,
          title: "Javascript",
          description: "Some course",
          status: false,
        },
      ],
    };
  },
  methods:{
    addTodo(newTodoObj){
      this.Todos=[...this.Todos,newTodoObj]
    },
    deleteTodo(todoId){
      console.log(todoId)
      this.Todos=this.Todos.filter((element,index)=>{
        return element.id!== todoId
      })
    }
  }
};
</script>

<template>
  <div id="app">
    <Todos v-bind:Todos="Todos"  v-on:app-delete-todo="deleteTodo"/>
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<style>
</style>
