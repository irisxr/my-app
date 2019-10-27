<template>
    <div>
        name:{{name}}<br/>
        isVisible:{{isVisible}}<br/>
        list:{{list}}<br/>
        type:{{type}}<br/>
        <button @click="handleThing">change thing</button>

    </div>
</template>


<style>

</style>


<script>
    export default {
        props: {
            name: String,
            isVisible: {
                type: Boolean,
                default: false,
            },
            list: {
                type: Array,
                default() {
                    return []
                },
            },
            type: {
                validator: function (value) {
                    return ['success', 'warning', 'danger'].includes(value)
                }
            },
            onChange: {
                type: Function,
                default:()=>{}
            },
        },
        methods:{
            handleThing(){
                //this.type='warning'
                this.onChange(this.type==='success'?'warning':'success')
            }
        }
    }
</script>