<template>
  <h1>John Reaction Time</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @reactionTime="getReactionTime"/>
  <Result v-if="showResult" :reactionTime="reactionTime"></Result>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
export default {
  name: 'App',
  components: {
    Block,
    Result
  },
  data(){
    return {
      isPlaying : false,
      delay:null,
      reactionTime:0,
      showResult : false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResult = false
    },
    getReactionTime(val){
      this.reactionTime = val
      this.isPlaying = false
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
