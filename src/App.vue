<template>
  <div id="app">
    <!-- <Test></Test> -->
    <!-- <img src="./assets/logo.png"> -->
    <!-- <img src="./assets/login.jpg"> -->
    <router-view/>
  </div>
</template>

<script>
// import Login from './components/login/Login';
export default {
  // components:{
  // Login,
  // },
  name: 'App'
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
