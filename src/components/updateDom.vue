<template>
    <div>
        props.customName:{{customName}}<br/>
        props.customInfo:{{customInfo}}<br/>
        props.customList:{{customList}}
    </div>
</template>

<script>
export default {
    props:{
        customName:String,
        customInfo:Object,
        customList:Array
    },

}
</script>