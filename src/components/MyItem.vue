<!--
 * @Descripttion: 
 * @version: 
 * @Author: sueRimn
 * @Date: 2021-09-16 21:06:41
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-18 17:00:50
-->
<template>
 <li>
   <label>
     <input type="checkbox" :checked="todo.done" @change="handlerCheck(todo.id)"/>
     <span>{{todo.title}}</span>
   </label>
   <button class="btn btn-danger" @click="handlerDelete(todo.id)" >删除</button>
 </li>
</template>

<script>
export default {
    name:'MyItem',
    props:['todo','checkTodo','deleteTodo'],
    methods: {
      //勾选
      handlerCheck(id){
        this.checkTodo(id);
      },
      //删除
      handlerDelete(id){
        if (confirm("确定删除么")) {
         this.deleteTodo(id);
        }
      }
    }
}
</script>
 
<style>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
li:hover { 
  background-color: #ddd;

}
li:hover button{
  display: block;
}
</style>