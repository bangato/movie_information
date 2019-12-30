<template>
  <div id="app">
    <Search v-on:SearchRequested="handleSearch"></Search>
    <Film v-bind:films=films></Film>    
  </div>
  
</template>

<script>

import Search from './components/search.vue'
import Film from './components/film.vue'

export default {
  name: 'app',
  components:{Search , Film},
  data(){
    return{
          films:[]
     }
  },
  methods:{
    handleSearch(query, query2){
      this.films=[];
     fetch('http://www.omdbapi.com/?s='+query+'&y='+query2+'&apikey=d727fc5a')
  .then((res) => { return res.json() } )
  .then((res) =>{ 
    this.films=res;
    
    //console.log(this.films.Error)
  })
    }
    },

    
    created(){
        fetch('http://www.omdbapi.com/?s=fast&apikey=d727fc5a')
        .then((res) => { return res.json() } )
        .then((res) =>{ 
          this.films=res;
       //console.log(this.films.Error)
        })
    }
  }

</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   */

   #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
} 

@import'~bootstrap/dist/css/bootstrap.css'
</style>