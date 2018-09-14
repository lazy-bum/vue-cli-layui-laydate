<template>
  <div class="hello">
    <p>你选择的日期是：{{ date }}</p>
    <p><input type="text" placeholder="点击选择日期" id="test1" v-model="date"></p>
  </div>
</template>
<script>
export default {
  name: "HelloLayData",
  data() {
    return {
      // 定义个变量用来存储选择的日期
      date: ""
    };
  },
  mounted() {
    // 使用：执行一个laydate实例
    laydate.render({
      elem: "#test1", // 指定元素
      type: "datetime", // 组建的类型：year,month,time···
      done: value => { // 点击确认执行的回调函数，会把当前选择的时间传入进来
        // 把选择的时间赋值给先前定义好的变量，显示在页面
        this.date = value;
      }
    });
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
