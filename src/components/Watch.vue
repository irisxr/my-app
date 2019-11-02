<template>
    <div>
        <p>FullName:{{fullName}}</p>
        <p>FirstName:<input type="text" v-model="firstName"></p>
        <p>LastName:<input type="text" v-model="lastName"></p>
    </div>
</template>
<script>
    export default{
        data(){
            return {
                firstName: '',
                lastName:''
            }
        },
        watch:{
            firstName(val){
                 this.fullName = val +' '+this.lastName
            },
            lastName(val){
                this.fullName = this.firstName +' '+val
            }
        }
    }
</script>