<template>
  <li>
    <div class="todo-item">{{ todo.todo }}</div>
    <button class="delete-todo" v-on:click="handleDeleteButton">
      delete
    </button>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: Object,
      required: true,
    },
    deleteTodo: Function,
  },
  methods: {
    handleDeleteButton() {
      this.deleteTodo(this.todo.id);
    },
  },
};
</script>

<style></style>
