<template>
  <div id="app">
    <custom-header />
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/Header';

export default {
  name: 'App',
  components: {
    'custom-header': Header,
  },
};
</script>
