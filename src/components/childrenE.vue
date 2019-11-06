<template>
    <div class="border2">
        <h3 :style="{color:theme.color}">E结点</h3>
    </div>
</template>

<script>
    export default {
        inject: {
            theme: {
                default: () => ({})
            }
        }
    }
</script>