<template>
    <div>
        <!--Conditional  rendering of Html-->
        <h2 v-if="num === 0">Number is zero</h2>
        <h2 v-else-if="num > 0">Number is Postive</h2>
        <h2 v-else-if="num < 0">Number is Negative</h2>
        <h2 v-else>Not a number</h2>
        <!-- Display  based on condtion without adding extra tag in dom-->
        <template v-if="display">
        <h2>Ankit</h2>
        <h2>Singh</h2>
       </template>
        <!--Using v-show directive-->
       <div v-show="display">
        <h2>Ankit</h2>
        <h2>Singh</h2>
       </div>
    </div>
</template>
<script>
export default {
    name:"ConditionalRendering",
    data(){
        return {
            num: 0,
            display:  false
        }
    }
}
</script>