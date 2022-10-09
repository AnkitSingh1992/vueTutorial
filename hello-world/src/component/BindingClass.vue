<template>
  <div>
    <!-- class binding -->
    <div class="underline">UnderLine</div>

    <!-- Binding class with dynamic data -->
    <div class="underline" v-bind:class="className">Dynamic class</div>

    <!-- Binding based on the condition-->
    <div v-bind:class="isPromoted && 'promoted'">Promoted Movie</div>

    <!--Binding class based on the ternary  operator-->
    <div v-bind:class="isSoldOut ? 'soldOut' : 'new'">Sold out Movie</div>

    <!--Binding mutiple class through array-->
    <div v-bind:class="['underline', 'new']">Newly promoted Movie</div>

    <!--Binding multiple class based on condtion through  array-->
    <div
      v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'soldOut' : 'new']"
    >
      Newly Promoted Movie through condtion
    </div>

    <!--Binding classes based on condition through object-->
    <div
      v-bind:class="{
        new: isSoldOut,
        promoted: isPromoted,
      }"
    >
      Adding class through Object
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      className: "success",
      isPromoted: true,
      isSoldOut: true,
    };
  },
};
</script>
<style>
.underline {
  text-decoration: underline;
}
.soldOut {
  color: red;
}
.new {
  color: green;
}

.promoted {
  font-style: italic;
}
</style>