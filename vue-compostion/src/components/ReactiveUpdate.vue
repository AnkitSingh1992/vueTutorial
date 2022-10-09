<template>
  <div>
     <h3>{{firstName}} {{lastName}}</h3>
  </div>
</template>

<script>
import {reactive,toRefs} from 'vue'
export default {
    name:'ReactiveUpdate',
    setup(){
        const state = reactive({
            firstName: 'Ankit',
            lastName:'Singh',
           
        });
        //setupTimeout
        setTimeout(()=>{
            console.log("Reactive time out")
            state.firstName = 'rahul',
            state.lastName = 'tiwari'
        },2000)

        return toRefs(state)           
    }

}
</script>

<style>

</style>