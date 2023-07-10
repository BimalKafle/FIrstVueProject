<template>
  <img alt="Vue logo" src="./assets/logo.png">
 <ModalComponent :header="header" :component="component" :theme="theme"/>
 
</template>

<script>

import ModalComponent from './components/ModalComponent.vue'
export default {
  name: 'App',
  components: {
    ModalComponent
  },
  data(){
    return{
      header:"Sign Up",
      component:"Please sign in to continue",
      theme:"sale"
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
}
</style>
