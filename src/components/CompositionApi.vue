<template>
  <div>
    <div>11</div>
    <p>{{count}}</p>
    <button @click="myFn">按钮</button>
    
    <h2>组合API本质：</h2>
    <p>{{name}}</p>
    <button @click="myFn1">按钮</button>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "CompositionApi",
  data() {
    return {
      name: "licheng"
    };
  },
  methods: {
    myFn1() {
      console.log("myFn1");
      this.name += "myFn1"
    }
  },
  // setup函数是组合API的入口函数
  setup() {
    // let count = 0;
    // 定义了一个名称叫做count变量，这个变量的初始值为0
    // 这个变量发生改变之后，Vue会自动更新UI
    let count = ref(0);
    // 在组合APIA中，如果像定义方法，不用定义到methods中，直接定义即可
    function myFn() {
      // alert("123");
      this.count++;
      // console.log(count);
      // console.log(this.count, count.value)
    }
    // 注意点：
    // 在组合API中定义变量/方法，要想在外界使用，必须return出去
    return { count, myFn };
  }
};
</script>

<style>
</style>