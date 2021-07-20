<template>
  <div id="app">
    <!-- Criando componente -->
    <Conversor moeda-a="USD" moeda-b="BRL"/>
  </div>
</template>

<script>
// importando componente
import Conversor from "./components/Conversor.vue"

// exportando App e definindo os componentes usados
export default {
  name: 'App',
  components: {
    Conversor
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
}
</style>
