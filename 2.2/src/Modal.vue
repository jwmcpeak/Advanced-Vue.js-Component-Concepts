<template>
    <div ref="modal" class="modal" tabindex="-1" role="dialog">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title">Modal title</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                <p>Modal body text goes here.</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary">Save changes</button>
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
