<template>
  <div class="home">
    <h1>{{calorie_count}}</h1>
    <form>
      <label for = "subcalories">Subtract: &nbsp;</label>
      <input v-model.number = "calorie_sub" type = "number"  min = "0" oninput="validity.valid||(value='');"> &nbsp;
      <button type= "button" class= "btn btn-primary" @click=result()>Subtract Calories</button>
      <br><br>
      <label for = "addcalories">Add: &nbsp;</label>
      <input v-model.number = "calorie_add" type = "number" min = "0" oninput="validity.valid||(value='');"> &nbsp;
      <button type= "button" class= "btn btn-primary" @click=add()>Add Calories</button>
    </form>
  </div>
</template>

<script>
// @ is an alias to /src
import Vue from 'vue'

export default {
  name: 'Home',
  data(){
    return{
      calorie_count: 3000,
      calorie_sub : 0,
      calorie_add: 0,
      //num: 0,
      result: function () {
        if(this.calorie_sub = ' '){
            this.calorie_sub = 0;
        }
          this.calorie_count = parseInt(this.calorie_count) - parseInt(this.calorie_sub);
      },
      add: function(){
        if(this.calorie_add = ' '){
            this.calorie_add = 0;
        }
        this.calorie_count = parseInt(this.calorie_count) + parseInt(this.calorie_add);
      },
      set_sub: function(num) {
        this.calorie_sub = parseInt(num);
      }
    }
  }
}
</script>
