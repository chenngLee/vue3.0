<template>
  <div>
    <form>
      <input type="text" v-model="state2.stu.name" />
      <input type="text" v-model="state2.stu.age" />
      <input type="submit" @click.prevent="addStu" value="提交" />
    </form>
    <ul>
      <li
        v-for="(item, index) in state.stus"
        :key="index"
        @click="remStu(index)"
      >{{item.name}} {{item.age}}</li>
    </ul>
  </div>
</template>
<script>
import { reactive } from "vue";

export default {
  setup() {
    // let state2 = reactive({
    //   stu: { age: "", name: "" }
    // });
    // let state = reactive({
    //   stus: [
    //     {
    //       age: 18,
    //       name: "小李"
    //     },
    //     {
    //       age: 20,
    //       name: "小王"
    //     }
    //   ]
    // });
    // function remStu(index) {
    //   state.stus = state.stus.filter((stu, idx) => idx != index);
    // }
    // function addStu() {
    //   const stu = Object.assign({}, state2.stu);
    //   state.stus.push(stu);
    //   state2.stu.age = "";
    //   state2.stu.name = "";
    // }
    let { state, remStu } = useRemoveStudent();
    let { state2, addStu } = useAddStudent(state);
    return { state2, state, addStu, remStu };
  }
};
function useRemoveStudent() {
  let state = reactive({
    stus: [
      {
        age: 18,
        name: "小李"
      },
      {
        age: 20,
        name: "小王"
      }
    ]
  });
  function remStu(index) {
    state.stus = state.stus.filter((stu, idx) => idx != index);
  }
  return { state, remStu };
}
function useAddStudent(state) {
  let state2 = reactive({
    stu: { age: "", name: "" }
  });
  function addStu() {
    const stu = Object.assign({}, state2.stu);
    state.stus.push(stu);
    state2.stu.age = "";
    state2.stu.name = "";
  }
  return { state2, addStu };
}
</script>
<style>
</style>