<template>
    <div>
        <div v-text="'Hi'"></div>
        <div v-html="'<span>Hi iris</span>'"></div>
        <div v-show="showMessage">show message</div>
        <button @click="showMessage=!showMessage">show</button>
        <div v-for="num in list" :key="num">{{num}}</div>
        <div v-if="number==1">number为1</div>
        <p>{{number}}</p>
        <button @click="number =number +1">add num</button>
    </div>
</template>

<script>
export default {
    data(){
        return{
            showMessage:true,
            list:[1,2,3],
            number:1
        }
    }
}
</script>