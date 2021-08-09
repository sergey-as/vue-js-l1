<template>
  <div id="app">
    <!--    <img alt="Vue logo" src="./assets/logo.png">-->
    <!--    v-bind: => expression-->
    <!--    <img v-bind:alt="imageAlt" v-bind:src="imageSrc">-->
    <img :alt="imageAlt" :src="imageSrc">
    <!--    <img :alt="2>3 ? imageAlt: 'kak'" :src="imageSrc+123">-->

    <!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <!--    <button @click="incCounter1">inc1 {{ counter1 }}</button>-->

    <div class="hello">{{ title }}</div>

    <ul>
      <!--      <li v-for="item of items" :key="item">{{ item }}</li>-->
      <li v-for="(item,index) of items" :key="item" @click="onListItemClic(item)">
        {{ item }} = {{ index }}

        <button @click="itemRemove(item,index)">remove</button>
      </li>

    </ul>

    <!--    <h1 v-if="counter % 2">HELLO</h1>-->
    <!--    <h1 v-if="counter === 0">HELLO</h1>-->
    <!--    <h1 v-else-if="counter === 1">1</h1>-->
    <!--    <h1 v-else-if="counter === 2">2</h1>-->
    <!--    <h1 v-else>WORLD</h1>-->
    <h1 v-show="counter === 0">WORLD</h1>

    <!--    <Counter />-->
    <!--    <Counter :counter="counter"/>-->
    <!--    <Counter :counter="counter" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <!--    <Counter :counter="counter" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <!--    <Counter :counter="counterVal()" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <!--    <Counter :counter="counterVal" @handleIncClick="incHandler" @handleDecClick="decHandler"/>-->
    <Counter :counter="counter" @handleIncClick="incHandler" @handleDecClick="decHandler"/>

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
      counter1: 0,
      title: 'Dynamic Text',
      imageAlt: 'Vue logo',
      imageSrc: Img,
      items: [1, 2, 3, 4]

      // Тримати методи у data не правильно, тому що data для даних:
      // clickHandler(){
      //   console.log('kak')
      // }
    }
  },
  methods: {
    onListItemClic(itemVal) {
      console.log(itemVal);
    },
    // itemRemove(item, index) {
    itemRemove(item) {
      // this.items.splice(index, 1)
      this.items = this.items.filter(el => el !== item);
    },
    // incHandler(arg, e) {
    incHandler(a, b, c) {
      // console.log(this)
      // console.log('inc', arg, e);
      console.log(a, b, c);
      this.counter++;
    },
    // incCounter1() {
    //   this.counter1++;
    // },
    // decHandler(e, arg) {
    decHandler() {
      // console.log('dec', arg, e);
      this.counter--;
    },
    // counterVal() {
    //   console.log(`recalculated str value`);
    //   return `Counter value is ${this.counter}`.toUpperCase().replaceAll(' ', '_')
    // }
  },
  // computed: {
  //   counterVal() {
  //     console.log(`recalculated str value`);
  //     return `Counter value is ${this.counter}`.toUpperCase().replaceAll(' ', '_')
  //   }
  // }
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

<!--arr-->
<!--conditions-->

<!--lifecycle-->