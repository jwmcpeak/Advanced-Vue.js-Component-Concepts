<template>
    <div ref="modal" class="modal" tabindex="-1" role="dialog">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" v-if="$slots.title">
                        <slot name="title"></slot>
                    </h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                    </button>
                </div>

                <div class="modal-body">
                    <slot></slot>
                </div>
                
                <div class="modal-footer" v-if="$slots.footer">
                    <slot name="footer"></slot>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import $ from 'jquery';
export default {
    props: ['show', 'backdrop'],
    watch: {
        show(value) {
            let el = $(this.$refs.modal);

            if (value) {
                let options = {
                    show: true
                };

                if (this.backdrop !== undefined) {
                    options.backdrop = this.backdrop;
                }


                el.modal(options);
            } else {
                el.modal('hide');
            }
        }
    },
    mounted() {
        $(this.$refs.modal).on('hide.bs.modal', () => {
            this.$emit('hide');
        });
    }
}
</script>
