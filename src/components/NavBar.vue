<template>
  <div id="nav-test">
    <img id="vue-logo" src="./logo.png">
      Heres a navbar and it's a component!!!
    <slot></slot>

    <div id="messageDivNav">{{ messageNav }}</div>
  </div>
</template>

<script>
  import EventBus from './EventBus.js'
  // import Button from './components/Button.vue'
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
