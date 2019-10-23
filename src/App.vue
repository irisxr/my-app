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
  </div>
</template>

<script>

import todoItem from './components/todoItem.vue'
export default {
  name: 'app',
    data(){
      return{
          info:'',
          list:[],
      }
    },
    methods:{
        addToDoItem(){
            this.list.push(this.info);
            this.info=''
        }
    },

  components: {
    todoItem,
  }
}
</script>

<style>

</style>
