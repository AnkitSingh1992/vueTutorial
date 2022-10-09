<template>
   <h2>PopUps</h2>
     <input type="text" placeholder="Enter the name" v-model="name"/>
    <button @click="$emit('close', name)">Close</button>
</template>

<script>
export default {
    name:"PopUps",
    data(){
        return {
            name:''
        }
    },
   // emits:['close']
   emits: {
      close:(name) => {
           if(!name){
            console.log("name should not be empty")
            return false;
           }else{
            return true;
           }
      }
   }

}
</script>

<style>

</style>