<template>
  <h1>Reaction Timer</h1>
  <button @click="startGame" :disabled="isPlaying">Play</button>
  <Block v-if="showBlock" @end="endGame"/>
  <Result v-if="showResult" :reactionTime="reactionTime"/>


  
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Block, Result
  },
  data () {
    return {
      isPlaying: false,
      showBlock: false,
      showResult: false,
      reactionTime: null
    }
  },
  mounted() {

  },
  methods: {
    startGame(){
      setTimeout(() => {
        this.showBlock = true
      }, 2000)
    },
    endGame(reactionTime) {
      this.isPlaying = false
      this.showBlock = false
      this.reactionTime = reactionTime
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
  button {
    background: #0faf87;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
  }
  button[disabled] {
    opacity: 0.2;
    cursor: not-allowed;
  }
</style>
