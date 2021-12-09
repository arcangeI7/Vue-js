<template>
  <div>
    <h3>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</h3>
    <h3>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</h3>
    <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo"  v-for="(todo,index) in todos" :key="index" v-bind:todo="todo"></todo>

  </div>
</template>

<script type = "text/javascript" >

import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },

  methods: {
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = !this.todos[todoIndex].done;
    },

    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },

  },
};
</script>
<style>
  h3{
   text-align: left;
   margin: 0px
  }
</style>
