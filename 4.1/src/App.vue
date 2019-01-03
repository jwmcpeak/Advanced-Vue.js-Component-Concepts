<template>
  <div id="app">
    <list :items="guitars">
      <a :href="`/guitars/${guitar.id}`" 
          slot-scope="{item: guitar, index}">
        {{guitar.name}}
      </a>
    </list>
    
  </div>
</template>

<script>
import List from './List.vue';
export default {
  components: {List},
  name: 'app',
  data() {
    return {
      guitars: [
        {id: 0, name: 'Les Paul'},
        {id: 1, name: 'Vela'},
        {id: 2, name: 'Starla'}
      ]
    };
  }
}
</script>

<style>
#app {
  padding: 10px;
  margin: 10px;
}
</style>
