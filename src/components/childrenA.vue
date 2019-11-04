<template>
    <div class="border">
        <h1>A结点</h1>
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
                theme:this
            }
        },
        data(){
            return{
                color:'blue'
            }
        },
        components:{
            childrenB,
            childrenC
        }
    }
</script>