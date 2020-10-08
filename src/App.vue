<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld />
    <CompositionApi />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import CompositionApi from "./components/CompositionApi.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    CompositionApi
  }
};
</script>
