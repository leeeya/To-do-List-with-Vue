<template>
  <section>
    <h1>Todo List</h1>
    <ul>
      <todo-item v-for="(todo, index) in todoList" v-bind:key="index">
        {{ todo }}
      </todo-item>
    </ul>
  </section>
</template>

<script>
import TodoItem from '@/components/TodoItem';

export default {
  components: {
    'todo-item': TodoItem,
  },
  props: {
    todoList: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style></style>
