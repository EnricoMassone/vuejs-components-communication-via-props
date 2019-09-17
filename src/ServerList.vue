<template>
  <ul class="list-group">
      <my-server 
        v-for="server in servers" 
        :key="server.id"
        :server="server">
      </my-server>
  </ul>  
</template>

<script>
  import Server from "./Server.vue";

  export default {
    data: function() {
      return {
        servers: [
          { id: 1, status: "Normal" },
          { id: 2, status: "Critical" },
          { id: 3, status: "Degraded" },
          { id: 4, status: "Critical" },
          { id: 5, status: "Normal" }
        ]
      }
    },

    components: {
      "my-server": Server
    }
  };
</script>

<style></style>
