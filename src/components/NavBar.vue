<template>
  <div id="nav-test">
    <img id="vue-logo" src="./logo.png">
      Heres a navbar and it's a component!!!
    <button id="nav_btn1" type="button" class="btn btn-primary" v-on:click.prevent="button1">Button 1</button>
    <button id="nav_btn2" type="button" class="btn btn-primary" v-on:click.prevent="button2">Button 2</button>
    <button id="nav_btn3" type="button" class="btn btn-primary" v-on:click.prevent="button3">Button 3</button>
    <button id="nav_btn4" type="button" class="btn btn-primary" v-on:click.prevent="button4">Button 4</button>
    <div id="messageDivNav">{{ messageNav }}</div>
  </div>
</template>

<script>
  import {EventBus} from './EventBus.js'
  export default {
    data () {
      return {
        count: 0,
        messageNav: 'Start clicking buttons!'
      }
    },
    methods: {
      button1: function() {
        this.messageNav = 'Button 1 was just clicked!!';
        // EventBus.$emit({message: self.$data.messageNav});
      },
      button2: function() {
        this.messageNav = 'Button 2 was just clicked!!';

      },
      button3: function() {
        this.messageNav = 'Button 3 was just clicked!!';

      },
      button4: function() {
        this.messageNav = 'Button 4 was just clicked!!';

      }
    }
  }
</script>

<style>
#vue-logo {
  height: 50px;
}
</style>
