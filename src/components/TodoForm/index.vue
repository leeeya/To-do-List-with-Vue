<template>
  <form>
    <input type="text" v-model="todo.todo" />
    <button type="submit" v-on:click="handleSubmitButton">add todo</button>
  </form>
</template>

<script>
export default {
  name: 'TodoForm',
  data() {
    return {
      todo: {
        id: Date.now(),
        todo: '',
      },
    };
  },
  methods: {
    handleSubmitButton() {
      if (!this.todo.todo) {
        // eslint-disable-next-line no-alert
        confirm('할 일을 입력해주세요');
        return;
      }
      this.$emit('addTodo', this.todo);
      this.todo.todo = '';
    },
  },
};
</script>

<style></style>
