<template>
    <!-- method property example-->
    <div>
        <h2>{{10 + 20}}</h2>
        <h2>{{add(2,5)}}</h2>
        <h2>{{mutiply(10)}}</h2>
    </div>
</template>
<script>
    
export default {
    name: "MethodProperty",
    data(){
       return {
          multiplierValue: 5
       }
    },
    methods:{
       add(a, b){
        return a + b
       },
       mutiply(num){
        return num * this.multiplierValue
       }
    }
}
</script>