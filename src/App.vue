<template>
  <div id="app">
    <!--    <img alt="Vue logo" src="./assets/logo.png">-->
    <!--    v-bind: => expression-->
    <!--    <img v-bind:alt="imageAlt" v-bind:src="imageSrc">-->
    <img :alt="imageAlt" :src="imageSrc">
    <!--    <img :alt="2>3 ? imageAlt: 'kak'" :src="imageSrc+123">-->

    <!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <div class="hello">{{ title }}</div>

    <!--    <Counter />-->
    <!--    <Counter :counter="counter"/>-->
    <!--    <Counter :counter="counter" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <!--    <Counter :counter="counter" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <Counter :counter="counterVal()" @handleIncClick="incHandler" @handleDecClick="decHandler"/>

    <!--    &lt;!&ndash;    <button v-on:click="clickHandler">inc</button>&ndash;&gt;-->
    <!--    &lt;!&ndash;    <button v-on:click="incHandler">inc</button>&ndash;&gt;-->
    <!--    <button @click="incHandler(123, $event)">inc</button>-->
    <!--    <button @click="decHandler($event,321)">dec</button>-->

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
  methods: {
    // incHandler(arg, e) {
    incHandler(a, b, c) {
      // console.log(this)
      // console.log('inc', arg, e);
      console.log(a, b, c);
      this.counter++;
    },
    // decHandler(e, arg) {
    decHandler() {
      // console.log('dec', arg, e);
      this.counter--;
    },
    counterVal() {
      return `Counter value is ${this.counter}`.toUpperCase().replaceAll(' ','_')
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

.hello {
  background: red;
  color: green;
}

</style>

<!--plan:-->
<!--basic structure-->
<!--embedding js into template-->
<!--props-->
<!--state-->
<!--components-->

<!--emitting events-->
<!--styling-->

<!--lifecycle-->