<template>
<div id="app">
  <h1>{{contadorSeg < 10 ? '0'+contadorSeg : contadorSeg }} Segundos</h1>
  <div class="botones">
    <button @click="iniciar(5)">5 segundos</button>
    <button @click="iniciar(10)">10 segundos</button>
    <button @click="iniciar(30)">30 segundos</button>
    <button @click="iniciar(60)">60 segundos</button>
  </div>
</div>
</template>

<script>
export default {
  name: "contador",

  data() {
    return {
      contadorSeg: 0,
      myIntervalo: null,
    };
  },

  methods: {
    iniciar(time) {
      this.contadorSeg = time;
      clearInterval(this.myIntervalo);
      this.myIntervalo = setInterval(() => {
        this.contadorSeg > 0 ? this.contadorSeg-- : clearInterval(this.myIntervalo);
        
      }, 1000);
      
    },
  },
};
</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  
}
</style>
