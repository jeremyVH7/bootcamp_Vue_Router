<template>
  <div id="nav-demo">
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
