<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
  <div id="app">
    <input type="text" v-model="info">
    <button @click="addToDoItem()">addItem</button>
    <ul>
      <todo-item v-for="item in list">
        <template v-slot:item="itemProps">
          <span :style="{fontSize: '30px',color:itemProps.checked ?'red':'blue'}">{{item}}</span>
        </template>
      </todo-item>
    </ul>

    <props
    name="Hello Iris"
    :isVisible="true"
    :type="type"
    :on-change="handleChange"
    >
    </props>
  </div>
</template>

<script>

import todoItem from './components/todoItem.vue'
import props from './components/props.vue'
export default {
  name: 'app',
    data(){
      return{
          info:'',
          list:[],
          type:'success'

      }
    },
    methods:{
        addToDoItem(){
            this.list.push(this.info);
            this.info=''
        },
        handleChange(val){
            this.type=val;
        }
    },

  components: {
    todoItem,
      props,
  }
}
</script>

<style>

</style>
