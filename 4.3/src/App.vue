<template>
  <div id="app">
    <!-- <list :items="guitars">
      <a :href="`/guitars/${guitar.id}`" 
          slot-scope="{item: guitar, index}">
        {{guitar.name}}
      </a>
    </list> -->

    <http url="guitars.json">
      <list slot-scope="{data}" :items="data.guitars">
        <a :href="`/guitars/${guitar.id}`" 
            slot-scope="{item: guitar, index}">
          {{guitar.name}}
        </a>
      </list>
    </http>

    <!-- <login></login> -->
    
  </div>
</template>

<script>
import Http from './Http.vue';
import List from './List.vue';
import Login from './LoginForm.vue';

export default {
  components: {List, Login, Http},
  name: 'app',
  // data() {
  //   return {
  //     guitars: [
  //       {id: 0, name: 'Les Paul'},
  //       {id: 1, name: 'Vela'},
  //       {id: 2, name: 'Starla'}
  //     ]
  //   };
  // }
}
</script>

<style>
#app {
  padding: 10px;
  margin: 10px;
}
</style>
