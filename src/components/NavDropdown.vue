<template>
  <select v-on:change="dropdownChange" style="color: black;">
    <option value="0" selected="selected">Make a Selection</option>
    <option value="1">Selection 1</option>
    <option value="2">Selection 2</option>
    <option value="3">Selection 3</option>
  </select>
</template>

<script>
  import EventBus from './EventBus.js'
  export default {
    data () {
      return {
        count: 0
      }
    },
    methods: {
      dropdownChange: function() {
        alert('Dropdown Component was just changed!!');
      }
    }
  }
</script>

<style>

</style>
