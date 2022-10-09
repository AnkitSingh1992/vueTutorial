<template>
      <h3>Counter :: {{count}}</h3>
     <button @click="incrementCount">Counter</button>

</template>

<script>
 import useCounter from '../composable/useCounter'
export default {
   name:'ClickCounter',
   setup(){
    const {count,incrementCount} = useCounter();
    return {
        count,incrementCount
    }
   }
}
</script>

<style>

</style>