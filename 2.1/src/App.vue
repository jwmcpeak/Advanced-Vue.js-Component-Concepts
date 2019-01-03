<template>
  <div id="app">
    <login-form></login-form>
  </div>
</template>

<script>
import LoginForm from './LoginForm.vue';
export default {
  name: 'app',
  components: {LoginForm}
}
</script>

<style>
#app {
  padding: 10px;
  margin: 10px;
}
</style>
