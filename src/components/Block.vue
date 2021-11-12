<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      
  </div>

</template>

<script>
export default {
    props:["delay"],
    data(){
        return{
            showBlock : false,
            score : 0,
            timer : null         
        }
    },
    methods:{
        startTimer(){
            this.timer=setInterval(() => {
                 this.score += 50
            }, 50);
        },

        stopTimer(){
            clearInterval(this.timer);
            console.log(this.score);
            this.$emit("endGame",this.score)
        }

       
    },
    mounted(){
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);     
    }
}
</script>

<style>
    .block{
        height: 300px;
        width: 300px;
        background: #37AfA9;
        margin: auto;
    }
</style>