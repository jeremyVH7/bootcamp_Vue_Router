<template>
  <div>
    <div id="app">
      <h1>{{ title }}</h1>
      <NavBar>
        <ul>
          <li><img id="vue-logo" src="./assets/logo.png"></li>
          <li><NavButton v-bind:routerTo="buttonLinks[0][0]" v-bind:buttonText="buttonLinks[0][1]"></NavButton></li>
          <li><NavButton v-bind:routerTo="buttonLinks[1][0]" v-bind:buttonText="buttonLinks[1][1]"></NavButton></li>
          <li><NavButton v-bind:routerTo="buttonLinks[2][0]" v-bind:buttonText="buttonLinks[2][1]"></NavButton></li>
        </ul>
      </NavBar>
      <router-view/>
    </div>
  </div>
</template>

<script>
import {EventBus} from './components/EventBus.js'
import NavBar from './components/NavBar.vue'
import NavButton from './components/NavButton.vue'
import NavDropdown from './components/NavDropdown.vue'
import NavSearch from './components/NavSearch.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Error404 from './components/Error404.vue'

export default {
  name: 'app',
  components: {
    NavBar: NavBar,
    NavButton: NavButton,
    Home: Home,
    About: About,
    Error404: Error404
  },
  data () {
    return {
      title: 'Vue Router Demo',
      buttonLinks: [
        ['/home', 'Home'],
        ['/about', 'About'],
        ['/error404', '404']
      ]
    }
  },
  methods: {

  },
  created: function () {
    // EventBus.$on('button-clicked', this.buttonClicked);
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
}

h1, h2 {
  font-weight: normal;
  padding-left: 40px;
}

body {
  background: grey;
}

ul {
  list-style-type: none;
}

li {
  display: inline-block;
}
</style>
