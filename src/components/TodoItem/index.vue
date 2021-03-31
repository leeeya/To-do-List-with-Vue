/* eslint-disable vue/valid-template-root */
<template>
  <li>
    <div class="todo-item">{{ todo }}</div>
    <button class="delete-todo" v-on="handleDeleteButton">delete</button>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: String,
      required: true,
    },
  },
  methods: {
    handleDeleteButton() {
      this.$emit('deleteTodo', this.todoItem.id);
    },
  },
};
</script>

<style></style>
