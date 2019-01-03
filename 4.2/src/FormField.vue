<script>
export default {
    props: ['label', 'type', 'value'],
    render(createElement) {
        return createElement('div', {class: 'form-group'}, [
            createElement('label', this.label),
            this.buildFormControl(createElement)
        ]);
    },
    methods: {
        buildFormControl(createElement) {
            let options = {
                class: {
                    'form-control': true
                },
                on: {
                    input: (e)=> this.$emit('input', e.target.value)
                }
            };

            if (this.type === 'textarea') {
                return createElement('textarea', options, this.value);
            }

            options.attrs = {
                value: this.value,
                type: this.type
            };

            return createElement('input', options);
        }
    }
}
</script>

