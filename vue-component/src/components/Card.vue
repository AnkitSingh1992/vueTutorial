<template>
    <div class="card" style="width: 18rem;">
  <div  class="card-title" >
     <slot name="header"></slot>
  </div>
  <div class="card-body">
    <slot></slot>
  </div>

  <div>
    <slot name="footer"></slot>
  </div>
</div>
</template>

<script>
export default {
    name:"CardComponent"

}
</script>

<style>

</style>