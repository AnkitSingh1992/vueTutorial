<template>
    <div>
        <h3>Hello {{firstName}} {{lastName}}</h3>
        <!-- send data from  child to parent through compositon API -->
        <button @click="sendEvent">Call Heroes</button>
    </div>
</template>

<script>
import {computed} from 'vue'
export default {
  name:'PropsChild',
  props:['firstName','lastName'],
  emits:['callHeroes'],
  setup(props,context){
    console.log("props",props)
    const fullName = computed(()=>{
        console.log("computed",props.firstName , props.lastName)
        return `${props.firstName} ${props.lastName}`
    })
    //emit
     function sendEvent(){
        console.log('sendEvent')
      context.emit('callHeroes', fullName.value)
     }

    return {
        fullName,
        sendEvent
    }
  }
}
</script>

<style>

</style>