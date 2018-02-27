<template>
  <div id="app">
    <br><br><br><br><br><br><br>
    
    <div class="vutton-logo">
      <img src="./assets/vutton.svg" alt="">
    </div>
    
    <br><br><br><br><br><br><br>
    
    <Vutton 
      :width="300" 
      :height="80"
      :strokeWidth="5"
      :strokeDash="250"
      strokeColorDefault="#42b983"
      strokeColorAni="#51e0a0"
      :duration="2"
      >
      <div>hover it!!!</div>
    </Vutton>
  </div>
</template>

<script>
import Vutton from 'vutton'
// import Vutton from './components/Vutton'

export default {
  name: 'App',
  components: {
    Vutton
  }
}
</script>

<style>
.vutton-logo {
  text-align: center;
}

.vutton {
  margin: 0 auto;
}
.vutton__text {
  font-size: 22px;
  letter-spacing: 0.2rem;
}

</style>
