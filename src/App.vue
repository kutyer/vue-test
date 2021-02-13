<template>
  <h1>{{ animal }} </h1>
  <h2>원숭이는 {{ food }} 을 좋아합니다.</h2>
  <h3 v-text="food"></h3>
  <input type="text" v-model="food">
  <div v-html="alertMessage"></div>
  <img v-bind:src="imageUrl" alt="random">
  <a :href="food">{{food}}</a>
  <hr/>
  <h2 v-bind:class="{red : food == 'apple', 'not-good' : food == 'rice'}">원숭이는 {{ food }} 을 좋아합니다.</h2>


  <hr/>
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
      imageUrl : "https://placeimg.com/100/100/any",
      naverUrl : "https://www.naver.com",
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
.oragne { color:orange }
.salmon { color:salmon }
.red { color:red }
.not-good { text-decoration: line-through; }
</style>
