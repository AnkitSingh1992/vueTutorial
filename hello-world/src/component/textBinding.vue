<template>
    <div>
    <!--for binding text in html template-->
     <div>{{greet}}  {{name}}</div>
     <div v-text="channel"></div>
     <!-- <div v-text="channel">Hello</div> -->
    </div>
</template>
<script>

export default {
    name : "TextBinding",
    data() {
       return {
         name:'Ankit',
         greet:'Hello',
         channel:'Network-A',
       }
    }
}
</script>