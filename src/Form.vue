<template>
  <form @submit="handleSubmit">
    <label class="label" for="name">
      Nome
      <input class="input" type="text" v-model="name" id="name">
    </label>
    <label class="label" for="width">
      Largura
      <input class="input" type="number" v-model.number="width" id="width">
    </label>
    <label class="label" for="height">
      Altura
      <input class="input" type="number" v-model.number="height" id="height">
    </label>
    <label class="label" for="bgColor">
      Cor de fundo
      <input class="input" type="text" v-model="bgColor" id="bgColor">
    </label>
    <label class="label" for="borderWidth">
      Tamanho da borda
      <input
        class="input"
        type="number"
        v-model.number="borderWidth"
        id="borderWidth"
      >
    </label>
    <label class="label" for="borderStyle">
      Tipo da borda
      <select class="input" v-model="borderStyle" id="borderStyle">
        <option value="none">none</option>
        <option value="dotted">dotted</option>
        <option value="dashed">dashed</option>
        <option value="solid">solid</option>
        <option value="double">double</option>
      </select>
    </label>
    <label class="label" for="borderColor">
      Cor da borda
      <input class="input" type="text" v-model="borderColor" id="borderColor">
    </label>
    <div>
      <p>Visualização de {{name || 'retângulo sem nome :('}}</p>
      <div
        :style="{width: `${width}px`,
                height: `${height}px`,
                backgroundColor: bgColor,
                border: `${borderWidth}px ${borderStyle} ${borderColor}`}"
      ></div>
    </div>
    <button class="button">Gerar</button>
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
    computed: {
      options() {
        const {
          name,
          width,
          height,
          bgColor,
          borderWidth,
          borderStyle,
          borderColor
        } = this

        return {
          name,
          width,
          height,
          bgColor,
          borderWidth,
          borderStyle,
          borderColor
        }
      }
    },
    data() {
      return {
        name: '',
        width: 200,
        height: 50,
        bgColor: 'red',
        borderWidth: 0,
        borderStyle: 'none',
        borderColor: 'transparent'
      }
    }
  }
</script>

<style scoped>
  .label {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 0 0;
  }

  .input {
    padding: 8px 16px;
  }

  .button {
    font-size: 18px;
    padding: 12px 40px;
    width: 100%;
    margin: 30px 0;
    cursor: pointer;
  }

  .input,
  .button {
    border-radius: 4px;
    transition: border 0.3s linear, box-shadow 0.4s linear;
    border: 1px solid var(--color-grey);
  }

  .input:hover {
    border: 1px solid var(--color-dark);
  }

  .input:focus,
  .button:focus {
    outline: 0;
    border: 1px solid var(--color-blue);
    box-shadow: 0 0 1px 1px var(--color-blue);
  }
</style>
