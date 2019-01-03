<template>
  <div id="app">
    
    <button class="btn btn-primary"
      @click.prevent="modalShown = true">
      Show Modal
    </button>

    <confirm-modal 
      :show="modalShown"
      @hide="modalShown = false"
      @confirm="deleteResource"
    >

      <template slot="title">Delete Resource?</template>

      <p>Are you sure you want to delete ...?</p>
    
    </confirm-modal>
  </div>
</template>

<script>
import ConfirmModal from './ConfirmModal.vue';
export default {
  components: {ConfirmModal},
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
