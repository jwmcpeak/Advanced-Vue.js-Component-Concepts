<template>
  <div id="app">
    
    <button class="btn btn-primary"
      @click.prevent="modalShown = true">
      Show Modal
    </button>

    <delete-modal 
      :show="modalShown"
      @hide="modalShown = false"
      @confirm="deleteResource"
    >

      <template slot="title">Delete Resource?</template>

      <p>Are you sure you want to delete ...?</p>
    
    </delete-modal>
  </div>
</template>

<script>
import DeleteModal from './DeleteModal.vue';
export default {
  components: {DeleteModal},
  name: 'app',
  data() {
    return {modalShown: false};
  },
  methods : {
    deleteResource() {
      alert('Resource deleted');
    }
  }
}
</script>

<style>
#app {
  padding: 10px;
  margin: 10px;
}
</style>
