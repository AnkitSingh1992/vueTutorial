<template>
   <div>
       <h3>{{name}}</h3>
       <button  class="btn btn-primary" @click="setupName">ChangeName</button>
       
        <h3>{{count}}</h3>
        <button  class="btn btn-primary" @click="increment">Increment</button>

        <h3>{{firstName}} {{lastName}}</h3>
        <button  class="btn btn-primary" @click="changeName">ChangeName</button>
   </div>
</template>

<script>
import {ref, reactive , toRefs} from 'vue'
export default {
  name:'MethodComponent',
  setup(){
    const count = ref(0);

    function increment(){
        count.value =  count.value + 1;
    }

   const state = reactive({
    firstName : 'Ankit',
    lastName: 'Singh'
   })

   function changeName(){
    state.firstName = "Rahul",
    state.lastName = 'tiwari'
   }

    return {
        count,
        increment,
        ...toRefs(state),
        changeName
    }
  },

  data(){
    return{
    name:"Ankit",
    }
  },
  methods: {
   setupName(){
    this.name = "MethodCall"
   }
  }
}
</script>

<style>

</style>