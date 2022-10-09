<template>
    <div>
    <!--Replace v-bind directive shortCut-->
    <div :style="highLight">ShortLand</div>
</div>
</template>
<script>
export default {
    name:"shortLand",
    data(){
      return {
        highLight: {
            color: 'red'
        }
      }
    }
}
</script>