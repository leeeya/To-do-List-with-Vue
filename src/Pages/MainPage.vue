<template>
  <div class="main">
    <todo-form v-on:addTodo="addTodo"></todo-form>
    <todo-list v-bind:todoList="todoList"></todo-list>
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm';
import TodoList from '@/components/TodoList';

export default {
  name: 'MainPage',
  data() {
    return {
      todoList: [],
    };
  },
  components: {
    'todo-form': TodoForm,
    'todo-list': TodoList,
  },
  created() {
    const todoList = JSON.parse(localStorage.getItem('todo'));

    if (!todoList) return;
    this.todoList = todoList;
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
      this.todoList.push(todo);
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
