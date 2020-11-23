<template>
 <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <title-component text='Mi Banco dinamico 2.0'/>
    <cuenta-component />
 </div>
</template>

<script>
import CuentaComponent from './components/CuentaComponent.vue'
import TitleComponent from './components/TitleComponent.vue'


export default {
  name: 'App',
  components: {
    TitleComponent,
    CuentaComponent,
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
