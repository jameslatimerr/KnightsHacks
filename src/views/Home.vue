<template>
  <div class="home">
    <h1>{{calorie_count}}</h1>
    <input v-model.number="calorie_sub">
    <button type="button" class="btn btn-primary" v-on:click=result()>Subtract Calories</button>
    <modal v-if="(modalData.showModal = true) && (/[a-zA-Z]/).test(calorie_sub)" @click = "popModal"></modal>
    <modal v-show = "showModal" @close = "closeModal"></modal>
    <br><br>
    <input v-model.number="calorie_add">
    <button type="button" class="btn btn-primary" v-on:click=add()>Add Calories</button>
    <modal v-if="(modalData.showModal = true) && (/[a-zA-Z]/).test(calorie_add)" @click = "popModal"></modal>
    <modal v-show = "showModal" @close = "closeModal"></modal>
  </div>
</template>

<script>
// @ is an alias to /src
import modal from '@/components/modal.vue'
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
  components: {modal},
  data(){
    return{
      modalData: {
        showModal: false,
        modalHeader: "Enter a definition an word",
      },
      calorie_count: 3000,
      calorie_sub : 0,
      calorie_add: 0,
      //num: 0,
      result: function () {
      
          this.calorie_count = parseInt(this.calorie_count) - parseInt(this.calorie_sub);
          if(this.calorie_count < 0){
            this.calorie_count = 0;
        }
      },
      add: function(){

        this.calorie_count = parseInt(this.calorie_count) + parseInt(this.calorie_add);
          if(this.calorie_count < 0){
            this.calorie_count = 0;
          }
      },
      set_sub: function(num) {
        this.calorie_sub = parseInt(num);
      }
    };
  },
  methods: {
    popModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    }
  },
};
</script>

