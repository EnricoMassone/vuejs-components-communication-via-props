<template>
  <div v-if="server">
    <h3>Server {{ server.id }}</h3>
    <form>
      <div class="form-group">
        <label>Status</label>
        <select class="form-control">
          <option
            v-for="status in statuses"
            :key="status"
            :value="status"
            :selected="status === server.status">
            {{ status }}
          </option>
        </select>
      </div>
    </form>
  </div>

  <div v-else>
    <p>
      No server selected
    </p>
  </div>
</template>

<script>
  export default {
    data: function() {
      return {
        statuses: ["Normal", "Degraded", "Critical"]
      };
    },

    props: {
      server: Object
    }
  }
</script>

<style>
</style>