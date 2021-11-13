<template>
  <div class="home">
    <h1>Calorie Calculator</h1>
    <h2>{{calorie_count}}</h2>
    <input v-model.number="calorie_sub">
    <h1></h1>
    
    <button type="button" class="btn btn-primary" v-on:click=result()>Subtract Calories</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Vue from 'vue'
/*
Vue.component('calorie_subtracter', {
  data: function () {
    <vue-number-input v-model="value"  inline controls></vue-number-input>

    return {
      count: 0
    }

  },
  template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
})
*/
export default {
  name: 'Home',
  data(){
    return{
      calorie_count: 3000,
      calorie_sub : 0,
      //num: 0,
      result: function () {
   this.calorie_count = parseInt(this.calorie_count) - parseInt(this.calorie_sub);
   if(this.calorie_count < 0){
     this.calorie_count = 0;
   }
    },
    set_sub: function(num) {
      this.calorie_sub = parseInt(num);
    }
    }

  }
}
</script>
