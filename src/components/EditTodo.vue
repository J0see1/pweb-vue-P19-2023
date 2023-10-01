<!-- EditTodo.vue -->
<template>
    <div>
      <div v-if="!editable">{{ todo.content }}</div>
      <input v-else v-model="editedContent" @keydown.enter="saveTodo" @keydown.esc="cancelEdit" @input="updateEditedContent" />
      <button @click="toggleEdit">{{ editable ? 'Cancel' : 'Edit' }}</button>
      <button v-if="editable" @click="saveTodo">Save</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      todo: Object,
    },
    data() {
      return {
        editable: false,
        editedContent: this.todo.content,
      };
    },
    methods: {
      toggleEdit() {
        this.editable = !this.editable;
      },
      saveTodo() {
        this.editable = false;
        this.$emit("save", this.editedContent);
      },
      cancelEdit() {
        this.editable = false;
        this.editedContent = this.todo.content;
      },
      updateEditedContent(event) {
        // Update editedContent as the user types
        this.editedContent = event.target.value;
      },
    },
  };
  </script>
  