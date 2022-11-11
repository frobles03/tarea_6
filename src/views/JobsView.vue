<template>
    <div class="Trabajos">
      <h1>bienvenido a la tarea 6</h1>
      <div class="post" v-for="job in jobs" v-bind:key="job._id">
        <strong> <router-link :to="{name:'job', params:{id:job._id}}">{{job.title}}</router-link>  </strong> , salario:{{ job.salary }}
       
      </div>
      
    </div>
  </template>
  
  <script>
  // @ is an alias to /src    lista de los trabajos y que si se apreta uno de esos traabajos ver que aplicantes 
  // import HelloWorld from '@/components/HelloWorld.vue'
  import axios from 'axios'
  export default {
    name: 'JobsView',
    data() {
      return {
        jobs: []
      }
    },
  
    mounted() {
      let vue = this;
      axios.get('//170.239.85.65:3000/jobs')
        .then(function (response) {
          vue.jobs = response.data;
          console.log(vue.jobs)
        })
    }
  }
  </script>
  