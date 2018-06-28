<template>
  <div>
    <div id="app">
      <h1>{{ title }}</h1>
      <NavBar>
        <ul>
          <li><img id="vue-logo" src="./assets/logo.png"></li>
          <li><NavButton v-bind:buttonText="buttonText[0]"></NavButton></li>
          <li><NavDropdown v-bind:dropdownItems="dropdownItems1"></NavDropdown></li>
          <li><NavButton v-bind:buttonText="buttonText[1]"></NavButton></li>
          <li><NavButton v-bind:buttonText="buttonText[2]"></NavButton></li>
          <li><NavDropdown v-bind:dropdownItems="dropdownItems2"></NavDropdown></li>
          <li><NavSearch v-bind:searchText="searchText" v-bind:searchBtnText="searchBtnText"></NavSearch></li>
          <li><div id="messageDiv">{{ message }}</div></li>
        </ul>
      </NavBar>
    </div>
  </div>
</template>

<script>
import {EventBus} from './components/EventBus.js'
import NavBar from './components/NavBar.vue'
import NavButton from './components/NavButton.vue'
import NavDropdown from './components/NavDropdown.vue'
import NavSearch from './components/NavSearch.vue'
export default {
  name: 'app',
  components: {
    NavBar: NavBar,
    NavButton: NavButton,
    NavDropdown: NavDropdown,
    NavSearch: NavSearch
  },
  data () {
    return {
      title: 'Navbar Component Demo',
      message: 'Click stuff',
      dropdownItems1: ['dropdown1 item 1', 'dropdown1 item 2', 'dropdown1 item 3', 'dropdown1 item 4'],
      dropdownItems2: ['dropdown2 item 1', 'dropdown2 item 2', 'dropdown2 item 3'],
      buttonText: [
        'Nav Button 1',
        'Nav Button 2',
        'Nav Button 3',
        'Nav Button 4'
      ],
      searchText: 'NavBar Search Component',
      searchBtnText: 'Search'
    }
  },
  methods: {
    buttonClicked: function(buttonMessage) {
      ////// Do some action after button was clicked
      this.message = buttonMessage;
    },
    searchRan: function(searchMessage) {
      ////// Do some action after button was clicked
      this.message = searchMessage;
    },
    dropdownChanged: function(dropMessage) {
      ////// Do some action after dropdown was selected
      if (dropMessage != '') {
        this.message = dropMessage;
      } else {
        this.message = 'Click stuff';
      }
    }
  },
  created: function () {
    EventBus.$on('button-clicked', this.buttonClicked);
    EventBus.$on('dropdown-changed', this.dropdownChanged);
    EventBus.$on('search-run', this.searchRan);
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: white;
  margin-top: 60px;
  background: #3A52C9;
}

h1, h2 {
  font-weight: normal;
  padding-left: 40px;
}

body {
  background: grey;
}

#messageDiv {
  width: 100%;
  height: 50px;
  color: white;
}
ul {
  list-style-type: none;
}
li {
  display: inline-block;
}
</style>
