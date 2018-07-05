<template>
  <div class="jumbotron text-center">
    <h1>{{headerText}}</h1>
    <p>{{pText}}</p>
  </div>
</template>

<script>
export default {
  name: 'About',
  data () {
    return {
      headerText: 'About',
      pText: 'Here is some information. This is the about page'
    }
  }
}
</script>

<style>
.jumbotron {
  color: #3A52C9;
}
</style>
