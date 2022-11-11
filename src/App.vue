<template>
  <nav>
    <router-link to="/jobs">Trabajos</router-link> |
    <router-link to="/about">Aplicantes</router-link> |
    
  </nav>
  <router-view/>
</template>
<!-- <script>
import AboutView from './views/AboutView.vue';

export default{
  components:{
    'AboutView':AboutView
  },



  
}

</script> -->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
