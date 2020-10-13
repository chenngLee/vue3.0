<template>
  <div>
    <HelloWorld />
    <hr />
    <CompositionApi />
    <hr />
    <ComTodoList />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import CompositionApi from "./components/CompositionApi.vue";
import ComTodoList from "./components/ComTodoList.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    CompositionApi,
    ComTodoList
  }
};
</script>
