<template>
  <div id="app">
    <p>
      <em>Counter: </em> <counterValue :value="count"></counterValue>
    </p>
    <p>
      <em>Clicks: </em> <counterValue :value="notificationList.length"></counterValue>
    </p>
    <buttons 
      :count="count" 
      v-on:increment-count="incrementCount"
      v-on:decrement-count="decrementCount"
      v-on:button-notify="notify">
    </buttons>
    <notification :notificationList="notificationList"></notification>
  </div>
</template>

<script>
import counterValue from "./Counter";
import notification from "./Notification";
import buttons from "./Buttons";

export default {
  name: "App",
  components: {
    counterValue,
    notification,
    buttons
  },
  // state
  data() {
    return {
      count: 2,
      notificationList: []
    };
  },
  methods: {
    incrementCount() {
      this.count++;
    },
    decrementCount() {
      this.count--;
    },
    notify() {
      this.notificationList.push({
        date: new Date()
      });
    }
  }
};
</script>

<style>
body {
  background-color: yellow;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 300%;
}
button {
  font-size: 2rem;
  margin: 0 0.5rem;
}
</style>
