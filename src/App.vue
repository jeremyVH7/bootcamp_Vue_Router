<template>
  <div>
    <div id="app">
      <h1>{{ title }}</h1>
      <NavBar>
        <ul>
          <li><router-link to="/"><img id="vue-logo" src="./assets/logo.png"></router-link></li>
          <li v-for='(link, i) in buttonLinks' :key='i'><NavButton v-bind:routerTo="link[0]" v-bind:buttonText="link[1]"></NavButton></li>
        </ul>
      </NavBar>
      <router-view/>

      <div id="nav-test"></div>
      <div class='row'>
        <div class="col-sm-10"></div>
        <div class="col-sm-2">
          <div class="row">
            <div class='col-sm-4'></div>
            <div class='col-sm-4 d-btn' id='d-u' v-on:click="moveUp"></div>
            <div class='col-sm-4'></div>
          </div>
          <div class="row">
            <div class='col-sm-4 d-btn' id='d-l' v-on:click="moveLeft"></div>
            <div class='col-sm-4'></div>
            <div class='col-sm-4 d-btn' id='d-r' v-on:click="moveRight"></div>
          </div>
          <div class="row">
            <div class='col-sm-4'></div>
            <div class='col-sm-4 d-btn' id='d-d' v-on:click="moveDown"></div>
            <div class='col-sm-4'></div>
          </div>
        </div>
      </div>

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

import TweenMax from "gsap/TweenMax";

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
        ['/about', 'About']

        // ['/error404', 'Error']
      ]
    }
  },
  methods: {
    moveUp: function() {
      TweenMax.to("#nav-test", 5, {y:0});
    },
    moveDown: function() {
      TweenMax.to("#nav-test", 15, {y:1000});
    },
    moveLeft: function() {
      TweenMax.to("#nav-test", 5, {x:0});
    },
    moveRight: function() {
      TweenMax.to("#nav-test", 5, {x:1000});
    }
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
  padding-right: 5px;
}
.d-btn {
  background: blue;
  height: 50px;
  width: 100%;
  cursor: pointer;
}
</style>
