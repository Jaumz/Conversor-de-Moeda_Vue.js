<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
    <div class="linha col-sm-12"> 
    <Conversor moeda-a="USD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha col-sm-12"> 
    <Conversor moeda-a="CAD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="CAD"/>
  </div>
  <div class="linha col-sm-12"> 
    <Conversor moeda-a="EUR" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="EUR"/>
  </div>
  </div>
</template>

<script>

import Conversor from './components/Conversor.vue';

export default {
  name: 'App',
  components: {
    Conversor
    }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #51CC60;
  margin-top: 60px;
  max-width: 900px;
  margin: auto;
}

.linha{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-top: 40px;
}

/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {
    .col-sm-12 {
      width: 100%;
      margin-bottom: 20px;}
}

</style>
