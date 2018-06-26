<template>
  <div id="nav-demo">
    <img id="vue-logo" src="../assets/logo.png">
    <div id="NavTextDiv">{{ NavText }}</div>

      <div class="col-xs-1"></div>
      <div class="col-xs-10">
        <slot></slot>
      </div>
      <div class="col-xs-1"></div>

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
