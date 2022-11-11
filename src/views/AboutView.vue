<template>
  <div class="Aplicantes">
    <h1>bienvenido a la tarea 6</h1>
    <div class="post" v-for="job in jobs" v-bind:key="jobId">
      <strong> {{ job._id.position }} {{job.email}}</strong> , salario:{{ job.salary }}
      
    </div>
   
  </div>
</template>

<script>
// @ is an alias to /src    lista de los trabajos y que si se apreta uno de esos traabajos ver que aplicantes 
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
    axios.get('//170.239.85.65:3000/jobs/635d786a2be73d03233ad3cd/applications')
      .then(function (response) {
        vue.jobs = response.data;
        console.log(vue.jobs)
      })
  }
}
</script>
