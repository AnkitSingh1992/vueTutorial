<template>
    <h3>Life cycle Child</h3>
</template>

<script>
export default {
    name:'LifeCycleChild',
    beforeCreate(){
        console.log('Child before created')
    },
    created(){
        console.log("Child created")
    },
    beforeMount(){
        console.log("Child before mount")
    },
    beforeUpdate(){
        console.log("Child before update")
    },
    updated(){
        console.log("Child updated")
    },
    beforeUnmount(){
        console.log("Child before unmount")
    },
    unmounted(){
        console.log("Child Unmounted")
    }

}
</script>

<style>

</style>