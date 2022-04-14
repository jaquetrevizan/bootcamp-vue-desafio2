<template>
<fieldset>
    <legend>Conversão de moedas</legend>
  <div>
    <label class="label" for="input-reais">Reais:</label>
    <input id="input-reais" v-model="reais" :disabled="resultado">
  </div>
  <div>
    <label for="input-cotacao">Cotação do dolar:</label>
    <input id="input-cotacao" v-model="cotacaoDolar"  :disabled="resultado">
  </div>
  <div>
    <button @click="limpar">Limpar</button>
    <button @click="calcular">Calcular</button>
  </div>
  <p  v-if="resultado">Conversão R${{ resultado }}</p>
  </fieldset>
</template>

<script>

export default {
  data() {
    return {
      reais: null,
      cotacaoDolar: null,
      resultado: null
    }
  },
  methods: {
    calcular() {
      this.resultado = (this.reais / this.cotacaoDolar).toFixed(2)
    },
    limpar() {
      this.reais = null
      this.cotacaoDolar = null
      this.resultado = null
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: block;
  margin: auto;
  max-width: 500px;
}
.label {
  margin-left: 80px;
}
input {
  margin: 0 0 10px 10px;
}
button:last-of-type {
  margin-left: 10px;
}
</style>
