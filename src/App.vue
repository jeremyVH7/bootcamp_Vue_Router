<template>
  <div>
    <div id="app">
      <h1>{{ title }}</h1>
      <NavBar>
        <NavButton v-bind:buttonText="buttonText[0]"></NavButton>
        <NavDropdown v-bind:dropdownItems="dropdownItems1"></NavDropdown>
        <NavButton v-bind:buttonText="buttonText[1]"></NavButton>
        <NavButton v-bind:buttonText="buttonText[2]"></NavButton>
        <NavDropdown v-bind:dropdownItems="dropdownItems2"></NavDropdown>
      </NavBar>
      <div id="messageDiv">{{ message }}</div>
    </div>
  </div>
</template>

<script>
import {EventBus} from './components/EventBus.js'
import NavBar from './components/NavBar.vue'
import NavButton from './components/NavButton.vue'
import NavDropdown from './components/NavDropdown.vue'
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
      message: '',
      dropdownItems1: ['dropdown1 item 1', 'dropdown1 item 2', 'dropdown1 item 3', 'dropdown1 item 4'],
      dropdownItems2: ['dropdown2 item 1', 'dropdown2 item 2', 'dropdown2 item 3'],
      buttonText: [
        'Nav Button 1',
        'Nav Button 2',
        'Nav Button 3',
        'Nav Button 4'
      ]
    }
  },
  methods: {
    buttonClicked: function(buttonMessage) {
      this.message = buttonMessage;
    },
    dropdownChanged: function(dropMessage) {
      this.message = dropMessage;
    }
  },
  created: function () {
    EventBus.$on('button-clicked', this.buttonClicked);
    EventBus.$on('dropdown-changed', this.dropdownChanged);
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
  height: 50px;
  color: white;
}
</style>
