<template>
  <div class='hello'>
    <custom-header></custom-header>
    <todo-form></todo-form>
    <todo-list></todo-list>
  </div>
</template>

<script>
import Header from '@/components/Header';
import TodoForm from '@/components/TodoForm';
import TodoList from '@/components/TodoList';

export default {
  name: 'MainPage',
  components: {
    'custom-header': Header,
    'todo-form': TodoForm,
    'todo-list': TodoList,
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
