<!--
 * @Descripttion:
 * @version:
 * @Author: sueRimn
 * @Date: 2021-09-11 23:15:28
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-11 23:17:55
-->
<template>
  <div>
    <h2>学生姓名：{{studentName}}</h2>
    <h2>学生年龄：{{studentAge}}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      studentName: '张三',
      studentAge: '18'
    }
  }
}
</script>

<style>

</style>