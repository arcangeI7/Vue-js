<template>
<div>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:addTodo="addTodo"></create-todo> 
    <button class='ui basic button icon' v-on:click="reset">Reset</button>

</div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
    
  },

  data() {
    return {
      todos: [{
        title: 'HTML exercise',
        project: 'PMUD',
        done: true,
      }, {
        title: 'CSS exercise',
        project: 'PMUD',
        done: false,
      }, {
        title: 'JavaScript exercise',
        project: 'PMUD',
        done: false,
      }],
      todos_og: [{
        title: 'HTML exercise',
        project: 'PMUD',
        done: true,
      }, {
        title: 'CSS exercise',
        project: 'PMUD',
        done: false,
      }, {
        title: 'JavaScript exercise',
        project: 'PMUD',
        done: false,
      }],
    };
  },

  methods: {
    addTodo(title) {
      this.todos.push({
        title: title.title,
        project: title.project,
        done: false,
      });
    },
    reset() {
      this.todos= JSON.parse(JSON.stringify(this.todos_og));
      },
    
  },

};

</script>


<style>
</style>
