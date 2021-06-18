<template>
  <div class="row mb-3">
      <div class="col-md-8 col-sm-12 mb-3">
          <input type="text" class="form form-control" 
          placeholder="Enter movie name" v-model="userSearch">
      </div>
      <div class="col-md-4 col-sm-12">
          <button class="btn btn-primary"
           style="width:100%" 
          v-on:click="searchPressed">
              Search a movie</button>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Search',
  data(){
      return {
          userSearch:''
      }
  },
  methods:{
      searchPressed: function(){
          this.$emit('searchPressed',this.userSearch)
      }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>