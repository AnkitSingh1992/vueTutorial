<template>
  <div>
    <h3>Current User ::{{userName}}</h3>
    <h3>Count ::{{count}}</h3>
    <h3>Profile {{firstName}} {{lastName}}</h3>
  </div>
</template>

<script>

import {inject, toRefs} from 'vue'
export default {
  name:'ProvideAndInject',
  setup(){
  const userName = inject('userName','DefaultUser');
  const count = inject('c_count',0)
   const profile = inject('profile',{})
  return{
    userName,
    count,
    ...toRefs(profile)
   }
  }
}
</script>

<style>

</style>