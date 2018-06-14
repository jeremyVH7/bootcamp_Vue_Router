<template>
  <div id="nav-demo">
    <img id="vue-logo" src="./logo.png">
      Heres a navbar and it's a component!!!
    <slot></slot>
    <div id="messageDivNav">{{ messageNav }}</div>
  </div>
</template>

<script>
  import {EventBus} from './EventBus.js'
  export default {
    data () {
      return {
        count: 0,
        messageNav: ''
      }
    }
  }
</script>

<style>
#vue-logo {
  height: 50px;
}
</style>
