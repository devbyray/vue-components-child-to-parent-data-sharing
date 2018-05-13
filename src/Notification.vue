<template>
    <div class="notification">
      <ol>
        <li v-for="item of notificationList">
          <strong>{{item.date | formatDate}}</strong>
        </li>
      </ol>
    </div>
</template>

<script>
export default {
  name: "counter",
  props: ["notificationList"]
};
</script>

<style>

</style>
