<template>
    <button type="button" class="btn btn-primary" v-on:click.prevent="buttonClick">{{buttonText}}</button>
</template>

<script>
  import {EventBus} from './EventBus.js'
  export default {
    data () {
      return {
        buttonMessage: ''
      }
    },
    props: ['buttonText'],
    methods: {
      buttonClick: function() {
        this.buttonMessage = this.buttonText + ' was just clicked!';
        EventBus.$emit('button-clicked', this.buttonMessage);
      }
    }
  }
</script>

<style>

</style>
