<template>
  <div>
    <form action>
      <input type="text" v-model="stu.id" placeholder="id" />
      <input type="text" v-model="stu.name" placeholder="name" />
      <input type="text" v-model="stu.age" placeholder="age" />
      <input type="submit" @click.prevent="addStu" />
    </form>
    <ul>
      <li
        v-for="(stu,index) in stus"
        :key="index"
        @click="remStu(index)"
      >{{stu.name}} --- {{stu.age}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      stus: [
        { id: 0, name: "zs", age: 10 },
        { id: 1, name: "ls", age: 20 },
        { id: 2, name: "ww", age: 60 }
      ],
      stu: {
        id: "",
        name: "",
        age: ""
      }
    };
  },
  methods: {
    remStu(index) {
      this.stus = this.stus.filter((item, idx) => idx != index);
    },
    addStu() {
      const stu = Object.assign({}, this.stu);
      this.stus.push(stu);
      this.stu.id = "";
      this.stu.name = "";
      this.stu.age = "";
    }
  }
};
</script>
