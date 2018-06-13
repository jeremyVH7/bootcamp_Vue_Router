<template>
  <div>
    <div id="app">
      <h1>{{ title }}</h1>
      <NavBar>
        <NavButton></NavButton>
        <NavDropdown></NavDropdown>
        <NavButton></NavButton>
        <NavButton></NavButton>
        <NavDropdown></NavDropdown>
      </NavBar>
    </div>
    <div id="messageDiv">{{ message }}</div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import NavButton from './components/NavButton.vue'
import NavDropdown from './components/NavDropdown.vue'
import EventBus from './components/EventBus.js'
export default {
  name: 'app',
  components: {
    NavBar: NavBar,
    NavButton: NavButton,
    NavDropdown: NavDropdown
  },
  data () {
    return {
      title: 'Navbar Component Demo',
      message: ''
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  background: #3A52C9;
}

h1, h2 {
  font-weight: normal;
}

body {
  background: grey;
}

#messageDiv {
  width: 100%;
  height: 200px;
  color: white;
}
</style>
