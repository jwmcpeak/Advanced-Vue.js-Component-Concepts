<template>
    <modal :show="show"
      @hide="$emit('hide')"
      backdrop="static"
    >

      <template slot="title">
          <slot name="title"></slot>
      </template>

      <slot></slot>

      <template slot="footer">
        <button class="btn btn-secondary"
            data-dismiss="modal"
        >
            Cancel
        </button>

        <button class="btn btn-primary"
            data-dismiss="modal"
            @click.prevent="$emit('confirm')"
        >
            OK
        </button>

      </template>
    

    
    </modal>
</template>

<script>
import Modal from './Modal.vue';
export default {
  components: {Modal},
  props: ['show']
  
}
</script>
