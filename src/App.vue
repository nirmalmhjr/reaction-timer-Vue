<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @endGame="endGame"/>
  <Result v-if="showResult" :result="result"/>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: { Block, Result },
  data(){
    return{ 
      isPlaying: false,
      delay: null,
      result: null,
      showResult: false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() *4000
      this.isPlaying = true
      console.log(this.delay);
    },
    endGame(reactionTime){
      this.result = reactionTime
      this.showResult = true
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
  color: #444;
  margin-top: 60px;
}
button{
  background: #0faf87;
  color:white;
  border: none ;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
