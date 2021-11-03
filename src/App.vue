<template>
  <div id="app">
    <!-- <TablaMultiplicar/>
    <Deportes/>
    <hr/>
    <SumaNumerosParent/> -->
    <Comics/>
  </div>
</template>

<script>
import Comics from './components/Comics.vue'
// import Deportes from './components/Deportes.vue';
// import SumaNumerosParent from './components/SumaNumerosParent.vue';
// import TablaMultiplicar from './components/TablaMultiplicar.vue';



export default {
  name: 'App',
  components: {
    Comics
    // TablaMultiplicar,
    // Deportes,
    // SumaNumerosParent
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
