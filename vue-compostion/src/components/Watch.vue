<template>
     <div>
        <input type="text" placeholder="Name" v-model="name"/>
        <hr/>
         <!--compostion watch-->
         <input type="text" placeholder="firstName" v-model="firstName"/>
         <input type="text" placeholder="lastName" v-model="lastName"/>

         <hr/>
         <input type="text" placeholder="firstName" v-model="fName"/>
         <input type="text" placeholder="lastName" v-model="lName"/>
         <input type="text" placeholder="HeroName" v-model="option.heroName"/>
     </div>
</template>

<script>
import {reactive, ref, toRefs, watch} from 'vue'
import _ from 'lodash'
export default {
   name:'WatchComponent',
   setup(){
      const firstName = ref('');
      const lastName = ref('')
      watch([firstName, lastName],(newValue,oldValue)=>{
        console.log("FirstName Fields",oldValue[0],":::",newValue[0])
        console.log("Last Fields",oldValue[1],":::",newValue[1])
      },{
        immediate: true
      })

      const  state = reactive({
        fName: '',
        lName:'',
        option: {
             heroName:''
        }
      })

    /*  watch(
        ()=>{
        return { ...state}
      },
      function(newValue, oldValue){       
        console.log("fName",oldValue.fName,":::",newValue.fName)
        console.log("lName",oldValue.lName,":::",newValue.lName)
      }) */

      watch(()=> state.fName, function(newValue,oldValue){
        console.log("fName",oldValue,":::",newValue)
      })
     
    //   Without cloneDeep the data is showing same
      watch(()=>_.cloneDeep(state.option),function(newValue,oldValue){
        console.log("HeroName",oldValue.heroName,":::",newValue.heroName) 
      },
      {
        deep: true
      })
      return {
        firstName,
        lastName,
        ...toRefs(state)
      }
   },
   data(){
    return {
      name:""
    }
   },
   watch: {
    name(newValue, oldValue){
        console.log(oldValue,":::",newValue)
    }
   }
}
</script>

<style>

</style>