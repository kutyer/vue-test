<template>
  <h1>{{ animal }} </h1>
  <h2>원숭이는 {{ food }} 입니다.!!</h2>
  <h3 v-text="food"></h3>
  <input type="text" v-model="food">
  <div v-html="alertMessage"></div>
  
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
 
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      animal : "Monkey",
      food : "apple",
      alertMessage : "<h2>경고!!</h2>",
    }
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
input { font-size: 20px; }
</style>
