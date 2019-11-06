<template>
    <div class="border">
        <h1>A结点</h1>
        <button @click="()=>changeColor()">change color</button>
        <children-b/>
        <children-c/>
    </div>
</template>
<script>
    import childrenB from './childrenB'
    import childrenC from './childrenC'

    export default {
        provide() {
            return {
                theme: this
            }

        },
        data() {
            return {
                color: 'blue'
            }
        },
        components: {
            childrenB,
            childrenC,
        },
        methods: {
            changeColor(color) {
                if (color) {
                    this.color = color
                } else {
                    this.color = this.color == 'blue' ? 'red' : 'blue'
                }
            }
        }
    }
</script>