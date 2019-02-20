<template>
  <form @submit="handleSubmit">
    <label class="label" for="name">
      Nome
      <input class="input" type="text" v-model="options.name" id="name">
    </label>
    <label class="label" for="width">
      Largura
      <input class="input" type="number" v-model.number="options.width" id="width">
    </label>
    <label class="label" for="height">
      Altura
      <input class="input" type="number" v-model.number="options.height" id="height">
    </label>
    <label class="label" for="bgColor">
      Cor de fundo
      <input class="input" type="text" v-model="options.bgColor" id="bgColor">
    </label>
    <button>Gerar!</button>
  </form>
</template>


<script>
  export default {
    name: 'app-form',
    methods: {
      handleSubmit: function(ev) {
        ev.preventDefault()

        this.$emit('submit', this.options)
      }
    },
    data() {
      return { options: { name: '', width: 200, height: 50, bgColor: 'red' } }
    }
  }
</script>
