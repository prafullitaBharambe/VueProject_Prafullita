<script>
import Todo from './Todo.vue'
export default {
    name:'Todos',
    components:{
        Todo
    },
    props:[
        "Todos"
    ]
    
}
</script>
<template>
    <div>
        <h1>To Do List</h1>
        <ul>
            <li v-bind:key="Todo.id" v-for="Todo in Todos">
                <Todo v-on:todos-delete-todo="$emit('app-delete-todo',Todo.id)" v-bind:Todo="Todo" />
            </li>
        </ul>
    </div>
</template>
<style>

</style>