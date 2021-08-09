<template>
  <div class="hello1">

    <!--    counter value is {{ counter }}-->
    {{ counter }}
    <br class="hello">

    <!--    <button @click="incHandler(123, $event)">inc</button>-->
    <!--    <button @click="decHandler($event,321)">dec</button>-->
    <!--    <button class="hello" v-on:click="inc">inc</button>-->
    <!--    <button :class="counter > 0 ? 'isInced' : 'isDeced'" v-on:click="inc">inc</button>-->
    <!--    <button :class="getClassName()" v-on:click="inc">inc</button>-->
    <!--    <button :class="['bold',getClassName()]" v-on:click="inc">inc</button>-->
    <!--        <button :class="{bold: true, isInced: counter > 0, isDeced: counter <= 0}" v-on:click="inc">inc</button>-->
<!--    <button :class="['bold',{isInced: counter > 0, isDeced: counter <= 0}]" @click="inc">inc</button>-->
    <button :class="['bold']" @click="inc">inc</button>
    <button v-on:click="$emit('handleDecClick')">dec</button>

  </div>
</template>

<script>
export default {
  props: {
    // counter: Number
    counter: {
      type: Number,
      // type: String,
      required: true
    }
  },
  methods: {
    inc() {
      this.$emit('handleIncClick', 1, 2, 3)
    },
    // getClassName() {
    //   return this.counter > 0 ? 'isInced' : 'isDeced';
    // }
  }
}
</script>

<style>
.hello1 {
  background: #2c3e50;
  color: darkorange;
}
</style>

<style scoped>
.hello {
  background: #2c3e50;
  color: darkorange;
}

.bold {
  font-weight: bold;
  font-style: italic;
}

.isInced {
  color: green;

}

.isDeced {
  color: red;
}
</style>
