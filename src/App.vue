<template>
  <div id="app">
    <strong @click="goToSignUp">Sign up</strong>
    <strong @click="goToLogin" class="login-link">Login</strong>
    <HelloWorld v-if="signUpVisible" msg="Welcome to Your Vue.js App"/>
    <Login :goToHome="goToHome" v-if="loginVisible"/>
    <Home v-if="mainPageVisible"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Login from './components/Login.vue'
import Home from './components/Home.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    Login,
    Home
  },
  data:()=>({
    "signUpVisible":true,
    "loginVisible":false,
    "mainPageVisible":false
  }),
  methods:{
    goToHome(){
      this.signUpVisible = false
      this.loginVisible = false
      this.mainPageVisible = true
    },
    goToLogin(){
      this.signUpVisible = false
      this.loginVisible = true
      this.mainPageVisible = false
    },
    goToSignUp(){
      this.signUpVisible = true
      this.loginVisible = false
      this.mainPageVisible = false
    },

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.login-link{
  margin-left:50px;
}
strong{
  text-decoration: underline;
  cursor: pointer;
}
</style>
