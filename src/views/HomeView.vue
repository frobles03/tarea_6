<template>
  <div class="home">
    <h1>bienvenido a la tarea 6</h1>
    <div class="post" v-for="job in jobs" v-bind:key="job._id">
      <h3> {{ job._id }}</h3>
      <h3> {{ job.title }}</h3>
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'HomeView',
  data() {
    return {
      jobs: []
    }
  },

  mounted() {
    let vue = this;
    axios.get('https://jobs-demo-api-js.herokuapp.com/jobs')
      .then(function (response) {
        vue.jobs = response.data;
        console.log(vue.jobs)
      })
  }
}
</script>
