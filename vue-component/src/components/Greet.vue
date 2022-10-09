<template>
    <!--display the props value in template-->
   <h3>Welcome {{username}} a.k.h {{heroName}}</h3>
</template>

<script>
export default {
    name:"Greet-component",
    // receive the props value from the parent component
    props: ['username','heroName']
}
</script>

<style>
</style>