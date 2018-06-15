<template>
  <div id="nav-demo">
    <img id="vue-logo" src="./logo.png">
    <div id="NavTextDiv">{{ NavText }}</div>
    <slot></slot>
  </div>
</template>

<script>
  import {EventBus} from './EventBus.js'
  export default {
    data () {
      return {
        NavText: "Heres a navbar and it's filled with components!"
      }
    }
  }
</script>

<style>
#vue-logo {
  height: 50px;
}
</style>
