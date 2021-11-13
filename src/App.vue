<template>
  <div id="app">
    <h1> Calorie Tracker </h1>
    <p> This is an application to calculate your caloric consumption </p>
      
    <button type="button" class="btn btn-primary">Input Caloric Intake</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      types: [
        'search'
      ]
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#in{
  text-align: center;
}
</style>
