<template>
    <form @submit.prevent="submit">
        <div class="card">
            <div class="card-body">

                <form-field 
                    label="Email Address"
                    type="email"
                    v-model="email"
                ></form-field>

                <form-field 
                    label="Message"
                    type="textarea"
                    v-model="message"
                ></form-field>

                <div class="form-group">
                    <button class="btn btn-primary">Login</button>
                </div>


            </div>
        </div>
    </form>
</template>
<script>
import FormField from './FormField.vue';
export default {
    components: {FormField},
    data() {
        return {
            email: 'foo@foo.com',
            message: ''
        };
    },
    methods: {
        submit() {
            console.log(`Email: ${this.email}`);
        }
    }
}
</script>
