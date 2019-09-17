<template>
  <ul class="list-group">
      <my-server 
        v-for="index in 5" 
        v-bind:key="index"
        v-bind:index="index">
      </my-server>
  </ul>  
</template>

<script>
  import Server from "./Server.vue";

  export default {
    components: {
      "my-server": Server
    }
  };
</script>

<style></style>
