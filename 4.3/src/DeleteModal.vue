<template>
  

    <confirm-modal 
        v-on="$listeners"
        v-bind="$attrs"
        confirm-button-class="btn-danger"
    >

        <template slot="title">
            <slot name="title"></slot>
        </template>

        <slot></slot>

        <template slot="confirm-button-text">Delete</template>

    </confirm-modal>

</template>

<script>
import ConfirmModal from './ConfirmModal.vue';
export default {
  components: {ConfirmModal},
}
</script>
