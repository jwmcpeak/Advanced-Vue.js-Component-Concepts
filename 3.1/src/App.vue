<template>
  <div id="app">
    
    <button class="btn btn-primary"
      @click.prevent="modalShown = true">
      Show Modal
    </button>

    <modal :show="modalShown"
      @hide="modalShown = false"
      :backdrop="false"
    >

    <p>Modal body text goes here.</p>
    <p>MOre content.</p>
    
    <template slot="footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
    </template>
    
    

    
    <template slot="title">This is the title</template>
    
    
    
    </modal>
  </div>
</template>

<script>
import Modal from './Modal.vue';
export default {
  components: {Modal},
  name: 'app',
  data() {
    return {modalShown: false};
  }
}
</script>

<style>
#app {
  padding: 10px;
  margin: 10px;
}
</style>
