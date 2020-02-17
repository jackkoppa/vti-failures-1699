<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <Component1/>
    <Component2/>
    <Component3/>
    <Component4/>
    <Component5/>
    <Component6/>
    <Component7/>
    <Component8/>
    <Component9/>

    <ComplexComponent1/>
    <!-- <ComplexComponent2/>
    <ComplexComponent3/>
    <ComplexComponent4/>
    <ComplexComponent5/>
    <ComplexComponent6/>
    <ComplexComponent7/>
    <ComplexComponent8/>
    <ComplexComponent9/> -->
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import Component1 from './components/Component1.vue';
import Component2 from './components/Component2.vue';
import Component3 from './components/Component3.vue';
import Component4 from './components/Component4.vue';
import Component5 from './components/Component5.vue';
import Component6 from './components/Component6.vue';
import Component7 from './components/Component7.vue';
import Component8 from './components/Component8.vue';
import Component9 from './components/Component9.vue';

import ComplexComponent1 from './components/ComplexComponent1.vue';
// import ComplexComponent2 from './components/ComplexComponent2.vue';
// import ComplexComponent3 from './components/ComplexComponent3.vue';
// import ComplexComponent4 from './components/ComplexComponent4.vue';
// import ComplexComponent5 from './components/ComplexComponent5.vue';
// import ComplexComponent6 from './components/ComplexComponent6.vue';
// import ComplexComponent7 from './components/ComplexComponent7.vue';
// import ComplexComponent8 from './components/ComplexComponent8.vue';
// import ComplexComponent9 from './components/ComplexComponent9.vue';

import { helper1 } from './helpers/helper1'
import { helper2 } from './helpers/helper2'
import { helper3 } from './helpers/helper3'
import { helper4 } from './helpers/helper4'
import { helper5 } from './helpers/helper5'

export default Vue.extend({
  name: 'App',
  components: {
    HelloWorld,
    Component1,
    Component2,
    Component3,
    Component4,
    Component5,
    Component6,
    Component7,
    Component8,
    Component9,
    ComplexComponent1,
    // ComplexComponent2,
    // ComplexComponent3,
    // ComplexComponent4,
    // ComplexComponent5,
    // ComplexComponent6,
    // ComplexComponent7,
    // ComplexComponent8,
    // ComplexComponent9
  },
  created() {
    helper1()
    helper2()
    helper3()
    helper4()
    helper5()
  }
});
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
