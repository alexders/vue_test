<!--
 * @Descripttion:
 * @version:
 * @Author: sueRimn
 * @Date: 2021-09-11 22:06:20
 * @LastEditors: sueRimn
 * @LastEditTime: 2021-09-11 23:18:20
-->
<template>
  <div class="s">
    <h2>学校名称：{{ schoolName }}</h2>
    <h2>学校地址：{{ adress }}</h2>
    <button @click="showName">点击提示学校名</button>
  </div>
</template>

<script>
export default {
  name: "atguigu",
  data() {
    return {
      schoolName: "尚硅谷",
      adress: "北京昌平",
    };
  },
  methods: {
    showName() {
      alert(this.schoolName);
    },
  },
};
</script>

<style>
.s{
  background-color: yellow;
}
</style>