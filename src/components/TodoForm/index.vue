/* eslint-disable no-alert */
<template>
  <form>
    <input type='text' v-model='todo'/>
    <button type='submit' v-on:click="handleSubmitButton">add todo</button>
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
        alert('할 일을 입력해주세요');
        return;
      }
      this.$emit('addTodo', this.todo);
      // eslint-disable-next-line no-console
      this.todo = '';
    },
  },
};
</script>

<style></style>
