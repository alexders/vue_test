<!--
 * @Descripttion: 
 * @version: 
 * @Author: sueRimn
 * @Date: 2021-09-16 21:06:59
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-19 20:17:23
-->
<template>
  <div class="todo-footer" v-show="total">
    <label>
      <input type="checkbox" :checked="isAll" @change="checkAll" />
    </label>
    <span>
      <span>已完成{{ doneTotal }}</span> / 全部{{ total }}
    </span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: "MyFooter",
  props: ["todos", "checkAllTodo", "clearAllTodo"],
  computed: {
    isAll() {
      return this.doneTotal === this.total && this.total > 0;
    },
    total() {
      return this.todos.length;
    },
    //计算已完成数量
    doneTotal() {
      // let i = 0;
      // this.todos.forEach((todo) => {
      // if (todo.done) {
      // i++;
      // }
      // });
      //高级写法，用reduce条件筛选出是true的
      return this.todos.reduce((pre, todo) => pre + (todo.done ? 1 : 0), 0);
    },
  },
  methods: {
    //全选或者全不选
    checkAll(e) {
      this.checkAllTodo(e.target.checked);
    },
    //清除所有已完成
    clearAll() {
      if (confirm("确认删除")) {
         this.clearAllTodo();
      }
     
    },
  },
};
</script>

<style>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>