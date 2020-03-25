<template  >
  <div id="app"  >
      <ticTacToe />
  </div>
</template>

<script>
import ticTacToe from './components/puzzle'

export default {
  name: 'app',
  components: {
    ticTacToe
  },
  data(){
    return{
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
 
}
</style>
