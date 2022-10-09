<template>
   <div>
      <h3>Life cycle Parent</h3>
      <button @click="isShow = false">Load Child</button>
      <div v-if="isShow === true">
      <LifeCycleChildVue/>
    </div>
   </div>
</template>

<script>
    import LifeCycleChildVue from './LifeCycleChild.vue'
export default {
  
    name:'LifeCycleParent',
    components:{
        LifeCycleChildVue
    },
    data(){
        return{
            isShow:true
        }
    },
    beforeCreate(){
        console.log('before created')
    },
    created(){
        console.log("created")
    },
    beforeMount(){
        console.log("before mount")
    },
    beforeUpdate(){
        console.log("before update")
    },
    updated(){
        console.log("updated")
    },
    beforeUnmount(){
        console.log("before unmount")
    },
    unmounted(){
        console.log("Unmounted")
    }


}
</script>

<style>

</style>