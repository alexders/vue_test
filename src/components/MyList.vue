<!--
 * @Descripttion: 
 * @version: 
 * @Author: sueRimn
 * @Date: 2021-09-12 16:15:08
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-18 16:56:04
-->
<template>
 <ul class="todo-main">
     <my-item 
     v-for="todoObj in todos" 
     :key="todoObj.id" 
     :todo="todoObj"
     :checkTodo='checkTodo'
     :deleteTodo='deleteTodo'
     ></my-item>
 </ul>
</template>

<script>
import  MyItem  from './MyItem.vue'
export default {
    name:'MyList',
    components: {MyItem},
    props:['todos','checkTodo','deleteTodo']
}
</script>

<style>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>