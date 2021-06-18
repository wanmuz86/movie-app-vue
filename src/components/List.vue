<template>
  <div>
      <div class="card p-5 mb-3 bg-light">
          <h2>This is movie 1</h2>
          <p>2003</p>
      </div>
      <div class="card p-5 mb-3 bg-light">
          <h2>This is movie 2</h2>
          <p>2003</p>
      </div>
      <div class="card p-5 mb-3 bg-light">
          <h2>This is movie 3</h2>
          <p>2003</p>
      </div>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: ['movies']
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>