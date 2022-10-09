<template>
   <div>
    <h3> Without ref: {{value}}</h3>
      <h3>Ref: {{name}}</h3>
   </div>  
</template>

<script>
import { ref } from 'vue';
export default {
   name:'RefUpdate',
    
   setup(){
     let value= 'Value'
     let name =  ref('Ankit');
     setTimeout(()=>{  
        console.log("TimeOut")    
        name.value = 'Rohan'
        value = 'newValue'
     },2000)

     return{
        name,
        value
     }
   }
}
</script>

<style>

</style>