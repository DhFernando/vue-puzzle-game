<template>
  <div>
    <div class="container">
      <div class="row ">
        <div class="col-12">
          <div class="row mt-1 mb-1">
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
        },
        imge:'../assets/1.jpg'
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
