<template>
  <form>
    <input type="text" v-model="todo" />
    <button type="submit" v-on:click="handleSubmitButton">add todo</button>
  </form>
</template>

<script>
export default {
  name: 'TodoForm',
  data() {
    return {
      todo: '',
    };
  },
  methods: {
    handleSubmitButton() {
      if (!this.todo) {
        // eslint-disable-next-line no-alert
        confirm('할 일을 입력해주세요');
        return;
      }
      /* eslint-disable no-console */
      this.$emit('addTodo', this.todo);
      this.todo = '';
    },
  },
};
</script>

<style></style>
