<template>
   <div>
    <h1>TabB component</h1>
    <input type="text" v-model="company" placeholder="company"/>  
  </div>
</template>

<script>

export default {  
   name:'TabB',
   data(){
    return{
        company:''
    }
   }

}
</script>

<style>

</style>