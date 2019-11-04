<template>
    <div class="border1">
        <h2>C结点</h2>
        <children-e/>
        <children-f/>
    </div>
</template>
<script>
    import childrenE from './childrenE.vue'
    import childrenF from './childrenF.vue'
    export default {
      components:{
          childrenE,
          childrenF
      }
    }
</script>