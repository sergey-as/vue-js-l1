<template>
  <div id="app">
    <!--    <img alt="Vue logo" src="./assets/logo.png">-->
    <!--    v-bind: => expression-->
    <!--    <img v-bind:alt="imageAlt" v-bind:src="imageSrc">-->
    <img :alt="imageAlt" :src="imageSrc">
    <!--    <img :alt="2>3 ? imageAlt: 'kak'" :src="imageSrc+123">-->

    <!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <div>{{ title }}</div>

    <!--    <Counter />-->
    <Counter :counter="counter"/>

<!--    <button v-on:click="clickHandler">inc</button>-->
    <button v-on:click="incHandler">inc</button>
    <button v-on:click="decHandler">dec</button>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Counter from "./components/Counter";
import Img from "./assets/logo.png"

export default {
  name: 'App',
  components: {
    //   HelloWorld,
    //   Counter: Counter
    Counter
  },
  data() {
    return {
      counter: 0,
      title: 'Dynamic Text',
      imageAlt: 'Vue logo',
      imageSrc: Img,

      // Тримати методи у data не правильно, тому що data для даних:
      // clickHandler(){
      //   console.log('kak')
      // }
    }
  },
  methods:{
    incHandler(){
      // console.log(this)
      this.counter++;
    },
    decHandler(){
      // console.log(this)
      this.counter--;
    }
    38:00

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

<!--plan:-->
<!--basic structure-->
<!--embedding js into template-->
<!--props-->
<!--state-->
<!--components-->
<!--styling-->
<!--lifecycle-->