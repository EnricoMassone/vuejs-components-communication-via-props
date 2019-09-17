<template>
  <div class="row">
      <div class="col-xs-12 col-sm-6">
          <my-server-list 
            :servers="servers"
            :onServerSelected="selectedServerChanged">

          </my-server-list>
      </div>
      <div class="col-xs-12 col-sm-6">
          <my-server-details 
            :server="selectedServer"
            :onServerStatusChanged="serverStatusUpdated">

          </my-server-details>
      </div>
  </div>
</template>

<script>
  import ServerDetails from "./ServerDetails.vue";
  import ServerList from "./ServerList.vue";

  export default {
    data: function() {
      return {
        selectedServer: null,
        servers: [
          { id: 1, status: "Normal" },
          { id: 2, status: "Critical" },
          { id: 3, status: "Degraded" },
          { id: 4, status: "Critical" },
          { id: 5, status: "Normal" }
        ]
      }
    },

    methods: {
      selectedServerChanged(server) {
        this.selectedServer = server;
      },

      serverStatusUpdated(serverId, updatedStatus) {
        this.servers = this.servers.map(server => {
          if (server.id === serverId) {
            return {
              id: server.id,
              status: updatedStatus
            };
          } else {
            return server;
          }
        });
      }
    },

    components: {
      "my-server-details": ServerDetails,
      "my-server-list": ServerList
    }
  };
</script>

<style>
</style>