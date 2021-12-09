<template>
  <div class='ui basic content  aligned segment'>
    <button class='ui basic button icon' v-on:click="openForm">
      Add Task<i class='plus icon'></i>
    </button>
    <div class='ui card' v-show="isCreating">
      <div class='content'>
        <div class='ui form'>
          <div class='field'>
            <label>Title</label>
            <input v-model="titleText" type='text' ref='title' defaultValue="" />
          </div>
          <div class='field'>
            <label>Subject</label>
            <input v-model="projectText" type='text' ref='project' defaultValue="" />
          </div>
            <button class='ui basic blue button' v-on:click="sendForm()">
              Create
            </button>
            <button class='ui basic red button' v-on:click="closeForm">
              Cancel
            </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titleText: '',
      projectText: '',
      isCreating: false,
    };
  },
  methods: {
    openForm() {
      this.isCreating = true;
    },
    closeForm() {
      this.isCreating = false;
    },
    sendForm() {
        const title = this.titleText;
        const project = this.projectText;

        if (this.titleText.length >0 && this.projectText.length >0) {
            
            this.$emit('addTodo', {
              title,
              project,
              done: false,
            });
            this.newTodoText = ''; 
        }
      
      this.isCreating = true;
    },
  },
};
</script>
