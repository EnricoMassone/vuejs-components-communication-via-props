<template>
  <li class="list-group-item">
    Server #{{ server.id }}
  </li>  
</template>

<script>
  export default {
    props: {
      server: {
        type: Object,
        required: true
      }
    }
  }
</script>

<style>
</style>