<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
const { io } = require("socket.io-client");
const socket = io("http://127.0.0.1:3001");

export default {
  name: 'App',
  components: {
    HelloWorld
  },
    mounted() {
        socket.on("connect", () => {
            console.log(socket.id);
        });
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
