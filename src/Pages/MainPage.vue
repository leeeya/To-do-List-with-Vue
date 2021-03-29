<template>
  <div class='main'>
    <todo-form v-on:addTodo='addTodo'></todo-form>
    <todo-list></todo-list>
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm';
import TodoList from '@/components/TodoList';

export default {
  name: 'MainPage',
  components: {
    'todo-form': TodoForm,
    'todo-list': TodoList,
  },
  methods: {
    addTodo(todo) {
      const prevTodoList = JSON.parse(localStorage.getItem('todo'));
      let todos = [];

      if (!prevTodoList) {
        todos = JSON.stringify([todo]);
      } else {
        todos = JSON.stringify([...prevTodoList, todo]);
      }
      localStorage.setItem('todo', todos);
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
