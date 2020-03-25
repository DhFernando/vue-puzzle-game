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
      <div class="row">
        <button @click="clicked('seven')">{{ coods.seven }}</button>
        <button @click="clicked('eight')">{{ coods.eight }}</button>
        <button @click="clicked('nine')" >{{ coods.nine }}</button>
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
          'four':4,  'five':5,  'six':6,
          'seven':7,  'eight':8, 'nine':'X'
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
       }else if(cood == 'four'){
           if(this.coods.one == 'X'){
             this.temp =  this.coods.four
             this.coods.four = this.coods.one
             this.coods.one = this.temp
             this.temp = null
           }else if(this.coods.five == 'X'){
             this.temp = this.coods.four
             this.coods.four = this.coods.five
             this.coods.five = this.temp
             this.temp =null
           }else if(this.coods.seven == 'X'){ 
             this.temp = this.coods.four
             this.coods.four = this.coods.seven
             this.coods.seven = this.temp
             this.temp
           }
       }else if(cood == 'five'){
          if(this.coods.two == 'X'){
            this.temp = this.coods.five
            this.coods.five = this.coods.two
            this.coods.two = this.temp
            this.temp = null
          }else if(this.coods.four == 'X'){
            this.temp  = this.coods.five
            this.coods.five = this.coods.four
            this.coods.four = this.temp
            this.temp =  null
          }else if(this.coods.six == 'X'){
            this.temp = this.coods.five
            this.coods.five = this.coods.six
            this.coods.six = this.temp
            this.temp = null
          }else if(this.coods.eight == 'X'){
            this.temp = this.coods.five
            this.coods.five = this.coods.eight
            this.coods.eight = this.temp
            this.temp = null
          }
       }else if(cood == 'six'){
          if(this.coods.three == 'X'){
            this.temp = this.coods.six
            this.coods.six = this.coods.three
            this.coods.three = this.temp
            this.temp = null
          }else if(this.coods.five == 'X'){
            this.temp = this.coods.six
            this.coods.six = this.coods.five
            this.coods.five = this.temp
            this.temp = null
          }else if(this.coods.nine == 'X'){
            this.temp = this.coods.six
            this.coods.six = this.coods.nine
            this.coods.nine = this.temp
            this.temp = null
          }
       }else if(cood == 'seven'){
         if(this.coods.eight == 'X'){ // -----------------8
           this.temp = this.coods.seven
           this.coods.seven = this.coods.eight
           this.coods.eight = this.temp  
            this.temp=null
         }else if(this.coods.four == 'X'){ // ---------4 
           this.temp = this.coods.seven
           this.coods.seven = this.coods.four
           this.coods.four = this.temp
           this.temp = null
         }
       }else if(cood == 'eight'){
          if(this.coods.seven == 'X'){ // -----------------7
           
           this.temp = this.coods.eight
           this.coods.eight = this.coods.seven
           this.coods.seven = this.temp
           this.temp=null
         }else if(this.coods.nine == 'X'){ // ---------9
         
           this.temp = this.coods.eight
           this.coods.eight = this.coods.nine
           this.coods.nine = this.temp
           this.temp=null
         }else if(this.coods.five == 'X'){ // ----------5
           this.temp = this.coods.eight
           this.coods.eight = this.coods.five
           this.coods.five = this.temp
           this.temp = null
         }
       }else if(cood == 'nine'){
         if(this.coods.eight == 'X'){ // --------------8
             this.temp = this.coods.nine
             this.coods.nine = this.coods.eight
             this.coods.eight =this.temp
             this.temp=null
           }else if(this.coods.six == 'X'){ // ----------------------------6
              this.temp = this.coods.nine
              this.coods.nine = this.coods.six
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
