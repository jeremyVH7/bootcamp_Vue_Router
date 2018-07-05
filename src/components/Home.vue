<template>
  <div class="jumbotron text-center">
    <h1>{{headerText}}</h1>
    <p>{{pText}}</p>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      headerText: 'Home',
      pText: 'Here is a killer home page'
    }
  }
}
</script>

<style>
.jumbotron {
  color: #3A52C9;
}
</style>
