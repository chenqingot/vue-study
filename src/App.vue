<template>
  <div id="app">
    <HelloWorld msg="实例"></HelloWorld>
    <P>{{plus(message)}}</P>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  data() {
    return {
      message: "Hello"
    };
  },
  components: {
    HelloWorld
  },
  methods: {
    plus(mes) {
      return mes
        .split("")
        .reverse()
        .join("");
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
