<template>
  <div class="detail container">
    <i class="fas fa-spinner fa-spin" v-if="loading"></i>
    <div v-if="!loading">
    <h1>{{movie.Title}}</h1>
    <img v-bind:src="movie.Poster"/>
    <p>{{movie.Plot}}</p>
    <p>{{movie.Writer}}</p>
    <p>{{movie.Actors}}</p>
    <p>{{movie.Genre}}</p>
    <p>{{movie.Awards}}</p>
    <div class="card bg-light my-3" v-for="rating 
    in movie.Ratings" 
    :key="rating.Source">
    <h3>{{rating.Source}}</h3>
    <p>{{rating.Value}}</p>
    </div> 
    </div>
  </div>
</template>

<script>

export default {
  name: "Detail",
  mounted:function (){
    setTimeout(function(){ 
      this.loading=false 
      if (!this.movie){
        this.message = "Connection to slow!"
      }
      }, 
      3000);
   
    fetch(`http://www.omdbapi.com/?i=${this.$route.params.imdbID}&apikey=87d10179`)
      .then(response => response.json())
      .then(data => {
        this.movie = data
        this.loading = false
      }).catch(err=>{
        this.loading = false
        this.message = "Connection to slow!"
        console.log(err);
      })
      ;
  },
  data(){
    return {
      movie:null,
      loading:true,
      message:""
    }
  },
  methods:{
   
  }
};
</script>
