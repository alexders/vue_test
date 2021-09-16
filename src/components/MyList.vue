<!--
 * @Descripttion: 
 * @version: 
 * @Author: sueRimn
 * @Date: 2021-09-12 16:15:08
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-16 23:49:20
-->
<template>
 <ul class="todo-main">
     <my-item></my-item>
 </ul>
</template>

<script>
import  MyItem  from './MyItem.vue'
export default {
    name:'MyList',
    components: {MyItem}
}
</script>

<style>

</style>