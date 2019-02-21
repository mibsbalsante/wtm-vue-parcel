<template>
  <div class="app">
    <h1 class="title">Adicione seus próprios retângulos!</h1>
    <app-form @submit="addToList"></app-form>
    <app-list :list="list"></app-list>
  </div>
</template>

<script>
  import Vue from 'vue'
  import AppForm from './Form'
  import AppList from './List'

  export default {
    name: 'app',
    methods: {
      addToList: function(values) {
        this.list.unshift({ ...values })
      }
    },
    components: { AppForm, AppList },
    data() {
      return { list: [] }
    }
  }
</script>

<style scoped>
  .app {
    max-width: 1000px;
    padding: 20px;
    margin: 0 auto;
  }

  .title {
    text-align: center;
  }
</style>
