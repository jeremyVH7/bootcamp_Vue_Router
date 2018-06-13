<template>
    <button type="button" class="btn btn-primary" v-on:click.prevent="button1">{{buttonText}}</button>
</template>

<script>
  import EventBus from './EventBus.js'
  export default {
    data () {
      return {
        count: 0,
        buttonText: 'Button Component'
      }
    },
    methods: {
      button1: function() {
        alert('Button Component was just clicked!!');
      }
    }
  }
</script>

<style>

</style>
