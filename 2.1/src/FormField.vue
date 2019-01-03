<template>
    <div class="form-group">
        <label>{{label}}</label>
        <input 
            :type="type"
            class="form-control"
            :value="value"
            @input="$emit('input', $event.target.value)"
        >
    </div>
</template>
<script>
export default {
    props: ['label', 'type', 'value']
}
</script>

