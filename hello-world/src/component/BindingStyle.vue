<template>
    <div>
        <!-- Adding style in Html tag-->
        <div v-bind:style="{
            color: highLightColor,
            fontSize: size+'px',
            padding: '20px'
        }">Inline style</div>

         <!-- Adding style from data method-->
        <div v-bind:style="headerStyle">Inline with object</div>

        <!--Adding multiplestyle from data method-->
        <div v-bind:style="[headerStyle,successMessage]">Multiple styles </div>
    </div>
</template>
<script>
export default {
    name : "BindingStyle",
    data(){
        return {
            highLightColor: 'red',
            size:35,
            headerStyle: {
                color: 'red',
            fontSize: 35+'px',
            padding: '20px'
            },
            successMessage:{
                backgroundColor:'green',
                padding:'50px'
            }
        }
    }
}
</script>
<style>

</style>