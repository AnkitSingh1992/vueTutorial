<template>
  <div>
    <h3>Props Parent</h3>
    <input type="text" placeholder="firstName" v-model="firstName"/>
    <input type="text" placeholder="lastName" v-model="lastName"/>
    <PropsChild :firstName="firstName" :lastName ="lastName" @callHeroes="callHeroes"/>
  </div>
</template>

<script>
import { ref } from 'vue'
import PropsChild from './PropsChild.vue';
export default {
    name: "PropsParent",
    components: { 
        PropsChild,
     },    
    setup() {
        const firstName = ref('');
        const lastName = ref('');
       function callHeroes(hero){
        alert(`heroes ${hero}`)
       } 
        return {
            firstName,
            lastName,
            callHeroes
        };
    },
  
}
</script>

<style>

</style>