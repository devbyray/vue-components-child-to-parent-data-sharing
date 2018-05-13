<template>
    <div class="buttons">
      <button v-on:click="increment">increment</button>
      <button v-on:click="decrement">decrement</button>
    </div>
</template>

<script>
export default {
  name: "counter",
  props: ["count"],
  // actions
  methods: {
    increment() {
      this.$emit("increment-count");
      this.notify();
    },
    decrement() {
      this.$emit("decrement-count");
      this.notify();
    },
    notify() {
      this.$emit("button-notify");
    }
  }
};
</script>

<style>

</style>
