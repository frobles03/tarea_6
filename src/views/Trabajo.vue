<template>
    <div class="Trabajo">
      <h1>bienvenido a la tarea 6</h1>
  
      <h1>trabajo 1</h1>
      <div class="post" v-if="job">     
        <strong>posicion:</strong> {{ job.jobId.position}} <strong> descripcion:</strong> {{ job.jobId.description}}
        <strong>mensaje del aplicante :</strong> {{ job.message}}
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
        job: null
        
        
      }
    },
   
  
    mounted() {
      let vue = this;
      axios.get('//170.239.85.65:3000/jobs/'+this.$route.params.id)
        .then(function (response) {
          vue.job= response.data;
          console.log(vue.job)
        })
         
        
  
        
    }
  }
  </script>
  