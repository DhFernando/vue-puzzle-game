<template>
  <div>
    <div class="container">
      <div class="row ">
        <div class="col-6 ">
            <div class="row mt-2 mb-4">
              <h3><strong><b>DH <span class="text-primary">puzzle</span></b></strong> -  Vue</h3>
            </div>
            <div class="row">
              <div class="border p-0" @click="clicked('one')">
                <img :src="require('@/assets/'+ coods.one.toString() +'.jpg')" />  
              </div>
              <div class="border p-0" @click="clicked('two')">
                <img :src="require('@/assets/'+ coods.two.toString() +'.jpg')" />  
              </div>
              <div class="border p-0" @click="clicked('three')" >
                <img :src="require('@/assets/'+ coods.three.toString() +'.jpg')" />
              </div>
            </div>
            <div class="row">
              <div class="border p-0" @click="clicked('four')">
                <img :src="require('@/assets/'+ coods.four.toString() +'.jpg')" /> 
              </div>
              <div class="border p-0" @click="clicked('five')">
                <img :src="require('@/assets/'+ coods.five.toString() +'.jpg')" /> 
              </div>
              <div class="border p-0" @click="clicked('six')" >
                <img :src="require('@/assets/'+ coods.six.toString() +'.jpg')" /> 
              </div>
            </div>
            <div class="row">
              <div class="border p-0" @click="clicked('seven')">
                <img :src="require('@/assets/'+ coods.seven.toString() +'.jpg')" /> 
              </div>
              <div class="border p-0" @click="clicked('eight')">
                <img :src="require('@/assets/'+ coods.eight.toString() +'.jpg')" />
              </div>
              <div class="border p-0" @click="clicked('nine')" >
                <img :src="require('@/assets/'+ coods.nine.toString() +'.jpg')" /> 
              </div>
            </div>
        </div>
        <div class="col-6 mt-4 border-right border-left ">
          <div class="row ml-1">
            <div class="col-12">
              
              <div class="row">
                <img style="height:400px; " class="mt-5" :src="require('@/assets/'+ imge +'.jpg')" /> 
              </div>
              <div class="row mt-3">
                  <!-- <button class="btn btn-success mr-3">Start</button> -->
                  <button class="btn btn-warning">Reset</button>
                  <strong class="mt-1 ml-5"> movement : {{count}}</strong>
              </div>
            </div>
          </div>
        </div>
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
          'one':8,  'two':6,  'three':4,
          'four':3,  'five':5,  'six':2,
          'seven':1,  'eight':7, 'nine':'X'
        },
        imge:'puzzle',
        count:0
      }
    },
    computed: {
      
    },
    methods:{
      movementCount(){
        this.count ++
        this.winCheck();
      },
      winCheck(){
        if(
          this.coods.one == 1 && 
          this.coods.two == 2 && 
          this.coods.three == 3 && 
          this.coods.four == 4 && 
          this.coods.five == 5 && 
          this.coods.six == 6 && 
          this.coods.seven == 7
        
          )
          {    alert("you win the game")     }
      },

      clicked(cood){
       if(cood == 'one'){
         if(this.coods.two == 'X'){ // -----------------2
         this.movementCount()
             
           this.temp = this.coods.one
           this.coods.one = this.coods.two
           this.coods.two = this.temp  
            this.temp=null
         }else if(this.coods.four == 'X'){ // ----------4 
         this.movementCount()
           this.temp = this.coods.one
           this.coods.one = this.coods.four
           this.coods.four = this.temp
           this.temp = null
         }
       }else if(cood == 'two'){
         if(this.coods.one == 'X'){ // -----------------1
         this.movementCount()
           
           this.temp = this.coods.two
           this.coods.two = this.coods.one
           this.coods.one = this.temp
           this.temp=null
         }else if(this.coods.three == 'X'){ // ---------3
         this.movementCount()
         
           this.temp = this.coods.two
           this.coods.two = this.coods.three
           this.coods.three = this.temp
           this.temp=null
         }else if(this.coods.five == 'X'){ // ----------5
         this.movementCount()
           this.temp = this.coods.two
           this.coods.two = this.coods.five
           this.coods.five = this.temp
           this.temp = null
         }
         
       }else if(cood == 'three'){ 
           if(this.coods.two == 'X'){ // --------------2
           this.movementCount()
             this.temp = this.coods.three
             this.coods.three = this.coods.two
             this.coods.two =this.temp
             this.temp=null
           }else if(this.coods.six == 'X'){ // ----------------------------6
           this.movementCount()
              this.temp = this.coods.three
              this.coods.three = this.coods.six
              this.coods.six = this.temp
              this.temp = null
           }
       }else if(cood == 'four'){
           if(this.coods.one == 'X'){
             this.movementCount()
             this.temp =  this.coods.four
             this.coods.four = this.coods.one
             this.coods.one = this.temp
             this.temp = null
           }else if(this.coods.five == 'X'){
             this.movementCount()
             this.temp = this.coods.four
             this.coods.four = this.coods.five
             this.coods.five = this.temp
             this.temp =null
           }else if(this.coods.seven == 'X'){ 
             this.movementCount()
             this.temp = this.coods.four
             this.coods.four = this.coods.seven
             this.coods.seven = this.temp
             this.temp
           }
       }else if(cood == 'five'){
          if(this.coods.two == 'X'){
            this.movementCount()
            this.temp = this.coods.five
            this.coods.five = this.coods.two
            this.coods.two = this.temp
            this.temp = null
          }else if(this.coods.four == 'X'){
            this.movementCount()
            this.temp  = this.coods.five
            this.coods.five = this.coods.four
            this.coods.four = this.temp
            this.temp =  null
          }else if(this.coods.six == 'X'){
            this.movementCount()
            this.temp = this.coods.five
            this.coods.five = this.coods.six
            this.coods.six = this.temp
            this.temp = null
          }else if(this.coods.eight == 'X'){
            this.movementCount()
            this.temp = this.coods.five
            this.coods.five = this.coods.eight
            this.coods.eight = this.temp
            this.temp = null
          }
       }else if(cood == 'six'){
          if(this.coods.three == 'X'){
            this.movementCount()
            this.temp = this.coods.six
            this.coods.six = this.coods.three
            this.coods.three = this.temp
            this.temp = null
          }else if(this.coods.five == 'X'){
            this.movementCount()
            this.temp = this.coods.six
            this.coods.six = this.coods.five
            this.coods.five = this.temp
            this.temp = null
          }else if(this.coods.nine == 'X'){
            this.movementCount()
            this.temp = this.coods.six
            this.coods.six = this.coods.nine
            this.coods.nine = this.temp
            this.temp = null
          }
       }else if(cood == 'seven'){
         if(this.coods.eight == 'X'){ // -----------------8
         this.movementCount()
           this.temp = this.coods.seven
           this.coods.seven = this.coods.eight
           this.coods.eight = this.temp  
            this.temp=null
         }else if(this.coods.four == 'X'){ // ---------4 
         this.movementCount()
           this.temp = this.coods.seven
           this.coods.seven = this.coods.four
           this.coods.four = this.temp
           this.temp = null
         }
       }else if(cood == 'eight'){
          if(this.coods.seven == 'X'){ // -----------------7
          this.movementCount()
           
           this.temp = this.coods.eight
           this.coods.eight = this.coods.seven
           this.coods.seven = this.temp
           this.temp=null
         }else if(this.coods.nine == 'X'){ // ---------9
         this.movementCount()
         
           this.temp = this.coods.eight
           this.coods.eight = this.coods.nine
           this.coods.nine = this.temp
           this.temp=null
         }else if(this.coods.five == 'X'){ // ----------5
         this.movementCount()
           this.temp = this.coods.eight
           this.coods.eight = this.coods.five
           this.coods.five = this.temp
           this.temp = null
         }
       }else if(cood == 'nine'){
         if(this.coods.eight == 'X'){ // --------------8
         this.movementCount()
             this.temp = this.coods.nine
             this.coods.nine = this.coods.eight
             this.coods.eight =this.temp
             this.temp=null
           }else if(this.coods.six == 'X'){ // ----------------------------6
           this.movementCount()
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
