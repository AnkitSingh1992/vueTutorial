<template>
     <div>
         <!--bind html element to template -->
        <div v-html="value"></div>
        <div v-html="hack"></div>
     </div>
</template>
<script>
export default {
   name : "HtmlBinding" ,
   data() {
    return {
        value : "<b>Html Binding</b>",
        hack :`<a href ="#" onclick ="alert('you r hacked!!')">Your site is hacked</a>`,
    }
   }
}
</script>