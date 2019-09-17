<template>
  <li 
    class="list-group-item"
    @click="onServerSelected(server)">
    Server #{{ server.id }}
  </li>  
</template>

<script>
  export default {
    props: {
      server: {
        type: Object,
        required: true
      },
      onServerSelected: {
        type: Function,
        required: true
      }
    }
  }
</script>

<style scoped>
  li {
    cursor: pointer;
  }

  li:hover {
    background-color: lightgray;
  }
</style>
