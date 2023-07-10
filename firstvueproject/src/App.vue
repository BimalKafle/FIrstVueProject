<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div v-if="showModal">
     <!-- <ModalComponent :header="header" :component="component" :theme="theme" @close="handleEvent"/> -->
     <ModalComponent2 @close="handleEvent">
      <h1>This is a second Model Slot</h1>
     </ModalComponent2>
  </div>
  <button @click="handleEvent">Show Modal</button>
 
</template>

<script>

// import ModalComponent from './components/ModalComponent.vue'
import ModalComponent2 from './components/ModalComponent2.vue'
export default {
  name: 'App',
  components: {
    // ModalComponent,
    ModalComponent2
  },
  data(){
    return{
      header:"Sign Up",
      component:"Please sign in to continue",
      theme:"sale",
      showModal:false
    }
  },
  methods:{
      handleEvent(){
       this.showModal=!this.showModal;    
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
