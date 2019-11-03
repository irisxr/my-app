<template>
    <div>
        <button v-show="show=!show">销毁</button>
        <button v-if="show" v-append-text="`hello ${number}`" @click="number=number+1">
            按钮
        </button>
    </div>
</template>
<script>
    export default {
        directives:{
          appendText:{
              bind(){
                  console.log('bind');
              },
              inserted(el,binging){
                  el.appendChild(document.createTextNode(binging.value));
                  console.log('inserted',el,binging);
              },
              update(){
                console.log('update');
              },
              componentUpdated(el,binging){
                  el.removeChild(el.childNodes[el.childNodes.length-1]);
                  el.appendChild(el.createTextNode(binging.value));
                  console.log('componentUpdated');
              },
              unbind(){
                  console.log('unbind');
              }
          }
        },
        data(){
            return {
                show:true,
                number:1
            }
        }
    }
</script>