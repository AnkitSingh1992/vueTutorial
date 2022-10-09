<template>
  <div>
    <h3>{{o_firstName}}</h3>
    <h3>Compostion {{c_firstName}}</h3>
    <h3>Compostion Hello {{greet}}</h3>
    <h3>Compostion Reactive {{greetHero}}</h3>
  </div>
</template>

<script>

import { ref , reactive} from 'vue';

export default {
  name:'DataComponent',
   //composition API
   setup(){
    const c_firstName = ref('alok');
     c_firstName.value = 'Dayana';
     // to get the value from the c_firstName
     const greet = c_firstName.value;
     const  profile= reactive({
      firstName:'Ansh',
      lastName:'singh'
     })

     const greetHero = `Hello ${profile.firstName} ${profile.lastName}`

    
    return{
        c_firstName,
        greet,
        greetHero
    }
   },
  data(){
    return {
        o_firstName:"Brush"
    }
  }
}
</script>

<style>

</style>