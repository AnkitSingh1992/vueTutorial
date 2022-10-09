<template>
   <div v-for="name in names" :key="name">
    <!-- <h3>{{name.firstName}} {{name.lastName}}</h3> -->
    <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
   </div>
</template>

<script>
export default {
  name:"NamedListComponent",
  data(){
    return{
        names:[
            {firstName:'Ankit',lastName:'Singh'},
            {firstName:'Rahul', lastName:'tiwari'},
            {firstName:'Roshan',lastName:'Ojha'}
        ]
    }
  }
}
</script>

<style>

</style>