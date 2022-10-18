<template>
<div class="block" @click="stopTime">
    
</div>
</template>

<script>
export default {
  data () {
    return {
      timer: null,
      responseTime: null,

    }
  },
  mounted(){
    this.timer = setInterval(() => {
      this.responseTime +=10
    }, 10)

  },
  methods: {
    stopTime() {
      clearInterval(this.timer)
      
      this.$emit("end", this.responseTime)
    }
  }

}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background:  #0faf87;;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>