<template>
    <ul>
        <li v-for="(item, index) in items" :key="index">
            <slot :item="item" :index="index"></slot>
        </li>
    </ul>
</template>
<script>
export default {
    props: ['items']
}
</script>

