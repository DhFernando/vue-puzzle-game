<template>
  <div>
    <div class="container">
      <div class="row">
      <button @click="clicked('one')">{{ coods.one }}</button>
      <button @click="clicked('two')">{{ coods.two }}</button>
      <button @click="clicked('three')" >{{ coods.three }}</button>
    </div>
    <div class="row">
      <button @click="clicked('four')">{{ coods.four }}</button>
      <button @click="clicked('five')">{{ coods.five }}</button>
      <button @click="clicked('six')" >{{ coods.six }}</button>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'puzzle',
  
  data(){
      return{
        temp:null,
        coods : {
          'one':1,  'two':2,  'three':3,
          'four':4,  'five':5,  'six':'X'
        }
      }
    },
    computed: {
      
    },
    methods:{
      clicked(cood){
       if(cood == 'one'){
         if(this.coods.two == 'X'){ // -----------------2
             
           this.temp = this.coods.one
           this.coods.one = this.coods.two
           this.coods.two = this.temp  
            this.temp=null
         }else if(this.coods.four == 'X'){ // ----------4 
           this.temp = this.coods.one
           this.coods.one = this.coods.four
           this.coods.four = this.temp
           this.temp = null
         }
       }else if(cood == 'two'){
         if(this.coods.one == 'X'){ // -----------------1
           
           this.temp = this.coods.two
           this.coods.two = this.coods.one
           this.coods.one = this.temp
           this.temp=null
         }else if(this.coods.three == 'X'){ // ---------3
         
           this.temp = this.coods.two
           this.coods.two = this.coods.three
           this.coods.three = this.temp
           this.temp=null
         }else if(this.coods.five == 'X'){ // ----------5
           this.temp = this.coods.two
           this.coods.two = this.coods.five
           this.coods.five = this.temp
           this.temp = null
         }
         
       }else if(cood == 'three'){ 
           if(this.coods.two == 'X'){ // --------------2
             this.temp = this.coods.three
             this.coods.three = this.coods.two
             this.coods.two =this.temp
             this.temp=null
           }else if(this.coods.six == 'X'){ // ----------------------------6
              this.temp = this.coods.three
              this.coods.three = this.coods.six
              this.coods.six = this.temp
              this.temp = null
           }
       }
      }
    }
}
</script>


<style scoped>
 
</style>
