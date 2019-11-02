<template>
    <div>
        <p>reverse message1:{{reverseMessage1}}</p>
        <p>reverse message2:{{reverseMessage2()}}</p>
        <p>{{now}}</p>
        <input v-model="message">
    </div>
</template>
<script>
    export default {
        data() {
            return {
                message: 'Hello Iris'
            }
        },
        computed: {
            reverseMessage1() {
                return this.message.split('').reverse().join('')
            },
            now() {
                return Date.now()
            }
        },
        methods: {
            reverseMessage2() {
                   return this.message.split('').reverse().join('')
            }
        }
    }
</script>