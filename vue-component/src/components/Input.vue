<template>
  <div>
    <hr/>
    <input type="text" placeholder="Name" :value= "modelValue"  @input="$emit('update:modelValue',$event.target.value)"/>
  </div>
</template>

<script>
export default {
  name:"InputComponent",
  props:{
    modelValue:String
  }
  
}
</script>

<style>

</style>