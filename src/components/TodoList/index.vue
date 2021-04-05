<template>
  <section>
    <h1>Todo List</h1>
    <ul>
      <todo-item
        v-for="todo in todoList"
        :key="todo.id"
        :todo="todo"
        :deleteTodo="deleteTodo"
      />
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
      type: Array,
      required: true,
    },
    deleteTodo: Function,
  },
  methods: {},
};
</script>

<style></style>
