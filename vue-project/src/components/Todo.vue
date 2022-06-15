<script>
export default {
    name:'Todo',
    props:[
        "Todo"
    ],
    methods:{
        markComplete(){
            this.Todo.status = !this.Todo.status
        },
        deleteTodo(){
            this.$emit('todos-delete-todo',this.Todo.id)
        }
    }

}
</script>
<template>
    <div v-bind:class="{'completed':Todo.status}">
        <p v-on:click="markComplete">{{Todo.title}}</p>
        <p>{{Todo.description}}</p>
        <p>{{Todo.status}}</p>
        <button v-on:click="deleteTodo">Delete Todo</button>
    </div>
</template>
<style>
.completed{
    color:blueviolet
}
</style>