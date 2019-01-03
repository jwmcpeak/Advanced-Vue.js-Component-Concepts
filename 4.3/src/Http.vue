<script>
import axios from 'axios';
export default {
    props: ['url'],
    data() {
        return {
            response: {}
        };
    },
    created() {
        axios.get(this.url).then(res => this.response = res.data);
    },
    render() {
        return this.$scopedSlots.default({
            data: this.response
        });
    }
}
</script>
