<template>
  <ul class="list-group">
      <my-server 
        v-for="server in servers" 
        :key="server.id"
        :server="server"
        :onServerSelected="onServerSelected">
      </my-server>
  </ul>  
</template>

<script>
  import Server from "./Server.vue";

  export default {
    props: {
      servers: {
        type: Array,
        required: true
      },
      onServerSelected: {
        type: Function,
        required: true
      }
    },

    components: {
      "my-server": Server
    }
  };
</script>

<style></style>
