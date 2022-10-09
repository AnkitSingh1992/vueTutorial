<template>
  <div>
    <h2>{{ name }}</h2>
    <!--Inline event handler-->
    <!-- <button v-on:mouseover="name = 'Rahul'">Change</button> -->

    <button v-on:mouseover="changeName($event),increment(1,$event) ">Change</button>
    <hr />
    <h2>{{ count }}</h2>
    <button @click="increment(1,$event)">Increment</button> &nbsp;
    <button v-on:click="decrement(1)">Decrement</button>
    <hr />
  </div>
</template>
<script>
export default {
  name: "EventHandling",
  data() {
    return {
      name: "Ankit",
      count: 0,
    };
  },
  methods: {
    changeName(event) {
      console.log("Change Name Event", event);
      this.name = "Rahul";
    },
    increment(num,event) {
        console.log("Increment event",event)
      this.count += num;
    },
    decrement(num) {
      this.count -= num;
    },
  },
};
</script>