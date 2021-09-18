<!--
 * @Descripttion:
 * @version:
 * @Author: sueRimn
 * @Date: 2021-09-11 23:19:19
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-18 17:44:22
-->
<template>
  <div id="root">
  <div class="todo-container">
    <div class="todo-wrap">
      <my-header :addTodo='addTodo'></my-header>
      <my-list :todos='todos' :checkTodo='checkTodo' :deleteTodo='deleteTodo'></my-list>
      <my-footer :todos='todos'></my-footer>
    </div>
  </div>
</div>

</template>

<script>
//引入组件
import MyHeader from "./components/MyHeader.vue";
import MyList from "./components/MyList.vue";
import MyFooter from "./components/MyFooter.vue";

export default {
  name: "App",
  components: { MyHeader,MyList, MyFooter},
   data() {
   return{
     todos:[
       {id:'0001',title:'吃饭',done:true},
       {id:'0002',title:'喝酒',done:false}, 
       {id:'0003',title:'烫头',done:true},
     ]
   }
 },
  methods:{
      //往前添加一个数据
   addTodo( todoObj){
      this.todos.unshift(todoObj);
   },
   //勾选or取消勾选todo
   checkTodo(id){
     //遍历数组
     this.todos.forEach((todo)=>{
       if (todo.id===id) {  //对比id一样的勾选项
         todo.done =!todo.done  //将done值取反
       }
     })
   },
   //通知删除数据
   deleteTodo(id){
     this.todos=this.todos.filter((todo)=>{
       return todo.id !== id
     })
   }
 }
};
</script>

<style>
/*base*/
body {
  background: #fff;
}

.btn {
  /* display: inline-block; */
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>