<template> 
  <div>
  <HelloWorld />
  <Watchers/>
  </div>
</template>

<script>
import HelloWorld from './component/HelloWorld';
import Watchers from './component/Watchers';
export default {
  name: 'App',
  components:{
    HelloWorld,
    Watchers
  },
   data() {
    return {
     firstName :"Ankit"
    }
    }
     
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
