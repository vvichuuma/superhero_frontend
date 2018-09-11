<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <button v-on:click="sup()">Fuck</button>

     
       <div v-for="data in datas">


       <h4>{{ data.name }}</h4>


       </div>
 
  </div>
</template>

<style>
</style>

<script>
 
 var axios = require('axios');
 // console.log(axios);


export default {
  data: function() {
    return {
      message: "Vishnu is a Computer Programmer",
      datas:[]
    };
  },
  created: function() {},
  methods: {

    sup :function() {

      console.log("Tony stark is the IRon Man");

      axios.get("http://localhost:3000/api/hero").then(function(response) {

            console.log(response.data.heroes);

            this.datas = response.data.heroes;

      }.bind(this));

 
    }


  },
  computed: {}
};
</script>