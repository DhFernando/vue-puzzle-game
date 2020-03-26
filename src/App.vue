<template  >
  <div id="app"  >
      <puzzle />
  </div>
</template>

<script>
import puzzle from './components/puzzle'

export default {
  name: 'app',
  components: {
    puzzle
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
