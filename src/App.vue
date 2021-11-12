<template><br><br><br><br><br><br>

    <h2>How Fast Can You Catch Me ?</h2><br>

    <div class="btn-control">
        <button @click="play" :disabled="isPlay">PLAY</button>
    </div><br>

    <div v-if="isPlay">
        <Block :delay="delay" @endGame="gameOver"/>
    </div>

    <div v-if="end">
      <Result :score="score"/>
    </div>
   
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  components:{
    Block,
    Result
  },
  data(){
    return{
      isPlay : false,
      delay : null,
      score : 0,
      end : false
    }
  },
  methods:{
    play(){
      this.isPlay = true;
      this.delay=2000+Math.random()*5000
    },
    gameOver(score){
      this.score = score;
      this.isPlay = false;
      this.end = true;
    }
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body{
    background: #E0F2F2;
  }

  h2{
    text-align: center;
    color: #37AfA9;
   
  }

  .btn-control{
   text-align: center;

  }

  button{
    width: 80px;
    height: 40px;
    font-size: 1.2em;
    font-weight: 900;
    color: azure;
    background: #2D8E87;
    border-radius: 10px;
  }

</style>