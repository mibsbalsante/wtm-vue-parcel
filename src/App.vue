<template>
  <input type="text" v-model="field">
</template>

<script>
  import Vue from 'vue'

  module.exports = {
    name: 'app',
    data() {
      return { field: 'initial value' }
    }
  }
</script>
