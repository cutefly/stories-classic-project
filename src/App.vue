<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png">
    <h1>Welcome to dynamic Components!</h1>
    <ul class="nav nav-tabs">
      <li v-for="page in pages" v-bind:key="page" :class="isActivePage(page) ? 'active' : ''">
        <a @click="setPage(page)">{{page | capitalize}}</a>
      </li>
    </ul>
    <component :is="activePage"></component>
    <!--
    <stories :stories="stories"></stories>
    <HelloWorld/>
    <login></login>
    <stories></stories>
    <register></register>
    -->
   </div>
</template>

<script>
import Vue from 'vue'
import Login from './components/Login.vue'
import Register from './components/Register.vue'
import Stories from './components/Stories.vue'
// import HelloWorld from './components/HelloWorld'

Vue.filter('capitalize', function (value) {
  return value.charAt(0).toUpperCase() + value.substr(1)
})

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Login,
    Register,
    Stories
  },
  data () {
    return {
      pages: [
        'stories',
        'register',
        'login'
      ],
      activePage: 'stories'
    }
  },
  methods: {
    setPage (newPage) {
      this.activePage = newPage
    },
    isActivePage (page) {
      return this.activePage === page
    }
  },
  /*
  data () {
    return {
      stories: [
        {
          plot: 'My horse is amazing.',
          writer: 'Mr. Weebl',
          upvotes: 28,
          voted: false
        },
        {
          plot: 'Narwhals invented Shish Kebab.',
          writer: 'Mr. Weebl',
          upvotes: 8,
          voted: false
        },
        {
          plot: 'The dark side of the Force is stronger.',
          writer: 'Darth Bader',
          upvotes: 52,
          voted: false
        },
        {
          plot: 'One does not simply walk into Mordor',
          writer: 'Boromir',
          upvotes: 74,
          voted: false
        }
      ]
    }
  },
  */
  created () {
    console.log('App')
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
