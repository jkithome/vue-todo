<template>
  <div class='ui centered card'>
    <div class='content'>
      <div class='ui centered card' v-show="!isEditing">
        <div class='content'>
            <div class='header'>
                {{ todo.title }}
            </div>
            <div class='meta'>
                {{ todo.project }}
            </div>
            <div class='extra content'>
                <span class='right floated edit icon' v-on:click="showForm">
                <i class='edit icon'></i>
              </span>
            </div>
        </div>
        <div class='ui bottom attached green basic button' v-show="todo.done" disabled>
            Completed
        </div>
        <div class='ui bottom attached red basic button' v-show="!todo.done">
            Complete
        </div>
      </div>
      <div class='ui form' v-show="isEditing">
        <div class='field'>
          <label>Title</label>
          <input type='text' ref='title' v-model="todo.title" >
        </div>
        <div class='field'>
          <label>Project</label>
          <input type='text' ref='project' v-model="todo.title" >
        </div>
        <div class='ui two button attached buttons'>
          <button class='ui basic blue button' v-on:click"hideForm">
            Close X
          </button>
        </div>
      </div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo'],
    data() {
      return {
        isEditing: false,
      };
    },
    methods: {
      showForm() {
        this.isEditing = true;
      },
      hideForm() {
        this.isEditing = false;
      },
    },
  };
</script>
