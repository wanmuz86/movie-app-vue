<template>
  <div>
      <div class="card p-5 mb-3 bg-light" v-for="movie in movies" 
      :key="movie.imdbID" v-on:click="openDetail(movie)">
      <div class="row">
          <div class="col-sm-4">
              <img v-bind:src="movie.Poster" class="img-fluid" />
          </div>
          <div class="col-sm-8">
          <h2>{{movie.Title}}</h2>
          <p>{{movie.Year}}</p>
          </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: ['movies'],
  methods:{
      openDetail:function(movie){
          this.$router.push(`detail/${movie.imdbID}`)
      }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>