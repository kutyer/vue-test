<template>

  <div>
    <ul>
      <template v-for="(animal, index) in animals" v-bind:key="index">
        <li v-if="animal != 'dog'">{{animal}}</li>
      </template>
    </ul>
  </div>

  <div>
    <ul>
      <li v-for="(user, index) in users" v-bind:key="index">
        이름은 {{user.name}}이고, 직업은 {{user.job}}입니다.
        <span v-for="(item, index2) in user.skill" v-bind:key="index2">{{item}}</span>
      </li>
    </ul>
  </div>

  <div>
    <h2 v-for="(animal, index) in animals" v-bind:key="index">{{animal}} 인덱스:{{index}}</h2>
  </div>

  <div>
    <h2 v-if="display">보입니다.if</h2>
    <h2 v-show="display">보입니다.show</h2>
  </div>

  <div>
    <h2>당신의 나이는 {{age}} 입니다.</h2>
    <p v-if="age > 18">당신은 어른입니다.</p>
    <p v-else-if="age > 13 && age < 19">당신은 청소년입니다.</p>
    <p v-else>당신은 어린이입니다.</p>
  </div>

  <hr/>
  <h1>{{ animal }} </h1>
  <h2>원숭이는 {{ food }} 을 좋아합니다.</h2>
  <h3 v-text="food"></h3>
  <input type="text" v-model="food">
  <div v-html="alertMessage"></div>
  <img v-bind:src="imageUrl" alt="random">
  <a :href="food">{{ food }}</a>
  <hr/>
  <h2 v-bind:class="{red : food === 'apple', 'not-good' : food === 'rice'}">원숭이는 {{ food }} 을 좋아합니다.</h2>


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
      animals:["monkey", "rat", "dog", "lion"],
      users:[
        {name:'길동', job:"개발자", gender:"male", skill : ["html", "css", "javascript"]},
        {name:'철수', job:"pm", gender:"female", skill : ["project manage"]},
      ],
      display : false,
      age:13,
      t_animal: "Monkey",
      food: "apple",
      alertMessage: "<h2>경고!!</h2>",
      imageUrl: "https://placeimg.com/100/100/any",
      naverUrl: "https://www.naver.com",
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

input {
  font-size: 20px;
}

.oragne {
  color: orange
}

.salmon {
  color: salmon
}

.red {
  color: red
}

.not-good {
  text-decoration: line-through;
}
</style>
