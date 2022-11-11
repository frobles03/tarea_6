<template>
  <div class="Aplicantes">
    <h1>bienvenido a la tarea 6</h1>

    <h1>trabajo 3</h1>
    <div class="post" v-for="job in jobs3" v-bind:key="job.jobId">     
      <strong>posicion:</strong> {{ job.jobId.position}} <strong> descripcion:</strong> {{ job.jobId.description}}
      <strong>mensaje del aplicante :</strong> {{ job.message}}
    </div>
    <h1>trabajo 2</h1>
    <div class="post" v-for="job in jobs2" v-bind:key="job.jobId">     
      <strong>posicion:</strong> {{ job.jobId.position}} <strong> descripcion:</strong> {{ job.jobId.description}}
      <strong>mensaje del aplicante :</strong> {{ job.message}}
    </div>

    <h1>trabajo 1</h1>
  </div>
  <div class="post" v-for="job in jobs1" v-bind:key="job.jobId">     
      <strong>posicion:</strong> {{ job.jobId.position}} <strong> descripcion:</strong> {{ job.jobId.description}}
      <strong>mensaje del aplicante :</strong> {{ job.message}}
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
      jobs3: []
      
      
    }
  },
  data2() {
    return {
      jobs2: []
      
      
    }
  },

  mounted() {
    let vue = this;
    axios.get('//170.239.85.65:3000/jobs/635d786a2be73d03233ad3cd/applications')
      .then(function (response) {
        vue.jobs3 = response.data;
        console.log(vue.jobs3)
      })
       let vue1 = this;
    axios.get('//170.239.85.65:3000/jobs/635d786a2be73d03233ad3cb/applications')
      .then(function (response) {
        vue1.jobs1 = response.data1;
        console.log(vue1.jobs1)
      })

      let vue2 = this;
      axios.get('//170.239.85.65:3000/jobs/635d786a2be73d03233ad3cc/applications')
      .then(function (response) {
        vue.jobs2 = response.data2;
        console.log(vue2.jobs2)
      })

      
  }
}
</script>
