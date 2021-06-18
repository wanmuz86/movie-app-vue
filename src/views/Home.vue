<template>
  <div class="container">
    <Search v-on:searchPressed="callApi" />
    <List v-bind:movies=movies />
  </div>
</template>

<script>
// @ is an alias to /src
import List from "@/components/List.vue";
import Search from "@/components/Search.vue";
export default {
  name: "Home",
  components: {
    List,
    Search
  },
  data(){
    return {
      movies:[]
    }
  },
  methods:{
    callApi:function(val){
      fetch(`https://www.omdbapi.com/?s=${val}&apikey=87d10179`)
      .then(response => response.json())
      .then(data => this.movies = data["Search"]);
    }
  }
};
</script>
