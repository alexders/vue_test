<!--
 * @Descripttion:
 * @version:
 * @Author: sueRimn
 * @Date: 2021-09-11 23:19:19
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-11 23:22:23
-->
<template>
  <div>
    <School></School>
    <Student></Student>
  </div>
</template>

<script>
//引入组件
import School from "./components/School.vue";
import Student from "./components/Student.vue";

export default {
  name: "App",
  components: {
    School,
    Student,
  },
};
</script>

<style>
</style>