<template>
  <p v-if="server">
    Server #{{ server.id }} has status {{ server.status }}
  </p>
  <p v-else>
    No server selected
  </p>
</template>

<script>
  export default {
    props: {
      server: Object
    }
  }
</script>

<style>
</style>