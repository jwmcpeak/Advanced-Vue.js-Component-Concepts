<template>
    <modal
      v-on="$listeners"
      v-bind="$attrs"
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
            <slot name="cancel-button-text">Cancel</slot>
        </button>

        <button class="btn"
            :class="confirmButtonClass || 'btn-primary'"
            data-dismiss="modal"
            @click.prevent="$emit('confirm')"
        >
            <slot name="confirm-button-text">OK</slot>
        </button>

      </template>
    

    
    </modal>
</template>

<script>
import Modal from './Modal.vue';
export default {
  components: {Modal},
  props: ['confirmButtonClass']
  
}
</script>
