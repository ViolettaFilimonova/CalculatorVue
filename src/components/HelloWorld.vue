<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div  class="grid ">
      <div class="item current">{{current || '0'}}</div>
      <div @click="clear" class="item">C</div>
      <div @click="calculation('+/-')" class="item">+/-</div>
      <div @click="calculation('%')" class="item">%</div>
      <div @click="calculation('/')" class="item operator">/</div>
      <div @click="number(7)" class="item">7</div>
      <div @click="number(8)" class="item">8</div>
      <div @click="number(9)" class="item">9</div>
      <div @click="calculation('X')" class="item operator">X</div>
      <div @click="number(4)" class="item">4</div>
      <div @click="number(5)" class="item">5</div>
      <div @click="number(6)" class="item">6</div>
      <div @click="calculation('-')" class="item operator">-</div>
      <div @click="number(1)" class="item">1</div>
      <div @click="number(2)" class="item">2</div>
      <div @click="number(3)" class="item">3</div>
      <div @click="calculation('+')" class="item operator">+</div>
      <div @click="number(0)" class="zero item">0</div>
      <div @click="dot" class="item">.</div>
      <div @click="equals" class="item operator">=</div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      current: '',
      previous: null,
      operator: null,
      num1: '',
      num2: '',
    }
  },
  methods:{
    number(num){
      this.current += num
    },
    clear(){
      this.current = ''
    },
    calculation(symbol){
      switch (symbol){
        case '-':
          console.log('-')
          this.operator = (a,b) => a - b
          this.current = ''
          break
        case '+':
          console.log('+')
          return  this.operator = (a,b) => a + b
          //break;
        case '/':
          console.log('/')
          return  this.operator = (a,b) => a / b
          //break;
        case 'X':
          console.log('x')
          return  this.operator = (a,b) => a * b
          //break;
        case '+/-':
          // if (a > 0 || a = 0){
          //   return  '-' + a
          // }else {
          //   return  '+' + a
          // }
          break;
        case '%':
          console.log('%')
          return  this.operator = (a) =>  a / 100
        default:
          console.log(`Sorry, we are out of }.`);
      }
    },
    equals(){

    },
    dot(){

    },
    bind(){

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.grid{
  margin: 60px  auto 0px;
  width: 600px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}
.zero{
  grid-column: 1/3;
}
.item{
  border: 1px solid black;
  padding: 15px;
  background-color: antiquewhite;
  font-size: 20px;
}
.current{
  grid-column: 1/5;
  background-color: #94ccff;
}
.operator{
  background-color: #c88bff;
}
</style>
