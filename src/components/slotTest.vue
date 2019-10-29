<template>
    <div>
        <slot name="item" v-bind="{value:'vue'}"></slot>
    </div>
</template>

<script>
    export default {
        props:['item']
    }

</script>