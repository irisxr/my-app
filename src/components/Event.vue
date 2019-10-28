<template>
    <div>
        name:{{name||"--"}}
        <input :value="name" @change="handleEvent">
        <div @click="handleDivButton">
            <button @click="handleClick">重置成功</button>
            <button @click.stop="handleClick">重置失败</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            name: String
        },
        methods: {
            handleEvent(e) {
                this.$emit('change', e.target.value)
            },
            handleDivButton(){
                this.$emit('change','')
            },
            handleClick(e){
               // e.stopPropagation()
            }
        }
    }
</script>