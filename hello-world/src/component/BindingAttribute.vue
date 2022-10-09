<template>
    <div>
    <!--Binding the attribute with the help of v-bind directives for the below-->
     <div v-bind:id="heading">Heading</div>
     <button v-bind:disabled="flag">Show</button>
   </div>
</template>

<script>
export default {
    name:"BindingAttribute",
    data(){
        return {
            heading:"heading",
            flag : false
        }
    }
}
</script>