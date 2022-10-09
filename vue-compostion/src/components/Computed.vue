<template>
     <div>
         <input type ="text" v-model="firstName"/>
         <input type="text" v-model="lastName"/>
        <h3>My Result :: {{fullName}}</h3>
        <hr/>
        <input type ="text" v-model="refFirstName"/>
         <input type="text" v-model="refLastName"/>
        <h3>My Result for Ref Computed:: {{computedFullName}}</h3>

        <hr/>
        <input type ="text" v-model="reactiveFirstName"/>
         <input type="text" v-model="reactiveLastName"/>
        <h3>My Result for Reactive Computed:: {{computedReactiveFullName}}</h3>
     </div>
</template>

<script>
 import {computed, reactive, ref, toRefs}  from 'vue'
export default {
  name: "ComputedComponent",
  setup(){
    const refFirstName = ref('');
    const refLastName = ref('');
    const computedFullName =  computed(function(){
    return `${refFirstName.value} ${refLastName.value}`
    })

    const state = reactive({
        reactiveFirstName: '',
        reactiveLastName:''
    })

    const computedReactiveFullName = computed(function(){
        return `${state.reactiveFirstName} ${state.reactiveLastName}`
    })
    return {
        refFirstName,
        refLastName,
        computedFullName,
        ...toRefs(state),
        computedReactiveFullName
    }
  },

  data(){
    return {
        firstName:'',
        lastName:''
     }
   },
   computed: {
     fullName(){
        return `${this.firstName} ${this.lastName}`
     }
   }
}
</script>

<style>
input {
    margin: 4px
}
</style>