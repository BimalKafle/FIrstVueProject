<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <div v-if="showModal">
     <ModalComponent :header="header" :component="component" :theme="theme" @close="handleEvent"/>
     <ModalComponent2 @close="handleEvent">
      <h1>This is a second Model Slot</h1>
      <template v-slot:links>
        <a href="#" class="btn btn-primary">Sign up</a>
        <a href="#" class="btn btn-primary">Log In</a>
      </template>

     </ModalComponent2>
  </div> -->
  <!-- <button @click="handleEvent">Show Modal</button>
  -->
  <h1>Samurai Reaction Timer</h1>
  <button @click="showTimer" :disabled="IsPlaying">Play</button>
  <p v-if="showResults"> Reaction Time :{{score}}</p>
  <Result v-if="showResults" :score="score"/>
  <Block v-if="IsPlaying" :delay="delay" @end="endGame"/>
  
</template>

<script>

// import ModalComponent from './components/ModalComponent.vue'
// import ModalComponent2 from './components/ModalComponent2.vue'
import Block from './components/BlockComponent.vue'
import Result from './components/ResultComponent.vue'
export default {
  name: 'App',
  components: {
    // ModalComponent,
    // ModalComponent2
    Block,
    Result
  },
  data(){
    return{
      // header:"Sign Up",
      // component:"Please sign in to continue",
      // theme:"sale",
      // showModal:false
      IsPlaying:false,
      delay:null,
      score:null,
      showResults:false,
    }
  },
  methods:{
  //     handleEvent(){
  //      this.showModal=!this.showModal;    
  // }
  showTimer(){
    this.delay=2000+Math.random()*5000;
    this.IsPlaying=true;
    this.showResults=false;
  },
  endGame(reactionTimer){
    this.score=reactionTimer;
    this.IsPlaying=false;
    this.showResults=true;
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
